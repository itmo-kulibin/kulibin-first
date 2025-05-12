<script>
    import { base } from '$app/paths';
    import { onMount } from 'svelte';
    import MapPoint from '$lib/components/MapPoint.svelte';
    import MapPopup from '$lib/components/MapPopup.svelte';

    export let points = [];
    export let lastClicked = {x:0,y:0};
    
    [
    {
        "posX": 0.151489835700362,
        "posY": 0.2304147465437788,
        "text": "1",
    },
    {
        "posX": 0.4288499025341131,
        "posY": 0.5862775217613927,
    },
    {
        "posX": 0.2970616725863739,
        "posY": 0.4160894518108054,
        "text": "8"
    }
    ].forEach(i => {points.push(i)});

    let actives = [];
    points.forEach(() => {actives.push(false)});

    let image;
    const mapClick = (e) => {
        lastClicked = {x: e.layerX / image.width / scale, y: e.layerY / image.height / scale};
    };

    onMount(() => {
        setInterval(() => {
            for (let i = 0; i < points.length; i++) {
                points[i].x = points[i].posX * image.width * scale;
                points[i].y = points[i].posY * image.height * scale;
            }
        }, 100);
    });

    const scaleMin = 3;
    const scaleMax = 30;
    let scale = 8;
    let scaleStep = 1;
    const zoomIn = () => {
        if (scale < scaleMax - scaleStep) {
            scale += scaleStep;
        }
    }
    const zoomOut = () => {
        if (scale > scaleMin + scaleStep) {
            scale -= scaleStep;
        }
    }
</script>

<div class="map-wrapper">
    <img bind:this={image} class="map" style:transform="scale({scale})" on:click={mapClick} src="{base}/map/map.svg" />
    {#each points as item, index}
        <MapPoint text={item.text}
                  bind:posX={item.x}
                  bind:posY={item.y}
                  customIcon={item.customIcon}
                  onClick={() => {actives[index]=true;}} />
        <MapPopup bind:active={actives[index]} />
    {/each}

    <div class="controls">
        <div class="button" on:click={zoomIn}>
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" xmlns="http://www.w3.org/2000/svg">
              <line x1="12" y1="5" x2="12" y2="19" />
              <line x1="5" y1="12" x2="19" y2="12" />
            </svg>
        </div>
        <div class="button" on:click={zoomOut}>
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" xmlns="http://www.w3.org/2000/svg">
              <line x1="5" y1="12" x2="19" y2="12" />
            </svg>
        </div>
    </div>
</div>


<style>
    .map-wrapper {
        width: 100%;
        height: calc(100vh - 80px);
        overflow: scroll;
        position: relative;
    }
    .map {
        transition: transform 0.2s;
        /* transform: scale(6.2); */
        transform-origin: top left;
    }

    .controls {
        position: fixed;
        right: 10px;
        bottom: 10px;
        z-index: 5;
    }
    .controls .button {
        background-color: #000957;
        width: 48px;
        height: 48px;
        color: #FFF2F2;
        border-radius: 5px;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        margin-top: 5px;
    }
</style>

