<script lang="ts">
    import { onMount } from 'svelte';
    import MapPopup from '$lib/components/MapPopup.svelte';
    import customization from '$lib/data/customization.json';
    import geoJsonData from '$lib/data/points.json';
    import pointsContent from '$lib/content/map.json';
    import type { LngLat } from '@yandex/ymaps3-types';
    import type { YMapDefaultMarkerProps } from '@yandex/ymaps3-default-ui-theme';


    // Static markers data
    export const markersGeoJsonSource: Omit<YMapDefaultMarkerProps, 'popup'>[] = [
        {
            coordinates: [30.304488, 59.941545] as LngLat,
            title: 'Кунсткамера',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[0] = true;
            }
        },
        {
            coordinates: [30.308515, 59.937515] as LngLat,
            title: 'Адмиралтейство',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[1] = true;
            }
        },
        {
            coordinates: [30.314896, 59.950143] as LngLat,
            title: 'Петропавловская крепость',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[2] = true;
            }
        },
        {
            coordinates: [30.334409, 59.933588] as LngLat,
            title: 'Российская национальная библиотека',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[3] = true;
            }
        },
        {
            coordinates: [30.283089, 59.921223] as LngLat,
            title: 'Площадь Кулибина',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[4] = true;
            }
        },
        {
            coordinates: [30.285518, 59.936735] as LngLat,
            title: 'Дом академиков',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[5] = true;
            }
        },
        {
            coordinates: [30.373135782446905, 59.94540639754347] as LngLat,
            title: 'Таврический сад',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[6] = true;
            }
        },
        {
            coordinates: [30.375969, 59.947685] as LngLat,
            title: 'Таврический дворец',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[7] = true;
            }
        },
        {
            coordinates: [30.441497, 59.880238] as LngLat,
            title: 'Петербургский стекольный завод',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[8] = true;
            }
        },
        {
            coordinates: [30.35216, 59.957615] as LngLat,
            title: 'Санкт-Петербургская Медико-Хирургическая академия',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[9] = true;
            }
        },
        {
            coordinates: [30.312946, 59.940925] as LngLat,
            title: 'Зимний дворец',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[10] = true;
            }
        },
        {
            coordinates: [30.302874, 59.940885] as LngLat,
            title: 'Петербургская Академия наук',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[11] = true;
            }
        },
        {
            coordinates: [30.428785, 59.932966] as LngLat,
            title: 'Российский государственный исторический архив',
            color: 'lavender',
            size: 'micro',
            iconName: 'fallback',
            onClick: event => {
                actives[12] = true;
            }
        }
    ];

    // Dynamic points from GeoJSON
    export let points = geoJsonData.features.map(feature => ({
        coordinates: feature.geometry.coordinates,
        text: feature.properties.iconCaption,
        description: feature.properties.description
    }));

    export let lastClicked = { x: 0, y: 0 };
    let actives = points.map(() => false);
    let map;
    let ymaps;

    onMount(async () => {
        await loadYmaps();
        await initMap();

        return () => {
            if (map) map.destroy();
        };
    });

    async function loadYmaps() {
        if (!window.ymaps3) {
            const script = document.createElement('script');
            script.src = 'https://api-maps.yandex.ru/3.0/?apikey=2621858c-c102-449a-8961-bd57d5d2e29a&lang=ru_RU';
            document.head.appendChild(script);

            await new Promise((resolve) => {
                script.onload = async () => {
                    ymaps = window.ymaps3;
                    await ymaps.ready;
                    resolve();
                };
            });
        } else {
            ymaps = window.ymaps3;
            await ymaps.ready;
        }
    }

    async function initMap() {
        const { YMap, YMapDefaultSchemeLayer, YMapDefaultFeaturesLayer } = ymaps;

        // Create map instance
        map = new YMap(
            document.getElementById('map-container'),
            {
                location: {
                    center: [30.31, 59.94],
                    zoom: 13
                }
            }
        );

        // Add default layers
        map.addChild(new YMapDefaultSchemeLayer({ customization }));
        map.addChild(new YMapDefaultFeaturesLayer());

        // Load default UI theme
        ymaps.import.registerCdn('https://cdn.jsdelivr.net/npm/{package}', '@yandex/ymaps3-default-ui-theme@latest');
        const { YMapDefaultMarker } = await ymaps.import('@yandex/ymaps3-default-ui-theme');

        // Add static markers
        markersGeoJsonSource.forEach(marker => {
            map.addChild(new YMapDefaultMarker(marker));
        });

    }
</script>

<div class="map-wrapper">
    <div id="map-container" class="yandex-map"></div>

    {#each points as item, index}
        <MapPopup
                bind:active={actives[index]}
                data={pointsContent[index]}
                style={`left: ${lastClicked.x}px; top: ${lastClicked.y}px`}
        />
    {/each}
</div>

<style>
    .map-wrapper {
        width: 100%;
        height: calc(100vh - 80px);
        /*position: relative;*/
    }

    .yandex-map {
        width: 100%;
        height: 100%;
    }
</style>
