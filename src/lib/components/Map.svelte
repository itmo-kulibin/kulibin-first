<script>
    import { base } from '$app/paths';
    import MapPoint from '$lib/components/MapPoint.svelte';
    import MapPopup from '$lib/components/MapPopup.svelte';

    export let points = [];
    export let lastClicked = {x:0,y:0};
    
    points.push({
        text: "test",
        customIcon: "herm",
        customIconHeight: 64, // default value
        posX: 240,
        posY: 220
    });
    let actives = [];
    points.forEach(() => {actives.push(false)});

    const mapClick = (e) => {
        lastClicked = {x: e.layerX, y: e.layerY};
    };
</script>

<div class="map-wrapper">
    <img class="map" on:click={mapClick} src="{base}/map/map.svg" />
    {#each points as item, index}
        <MapPoint text={item.text}
                  posX={item.posX}
                  posY={item.posY}
                  customIcon={item.customIcon}
                  onClick={() => {actives[index]=true;}} />
        <MapPopup bind:active={actives[index]} />
    {/each}
</div>


<style>
    .map-wrapper {
        width: 100%;
        height: calc(100vh - 80px);
        overflow: scroll;
        position: relative;
    }
    .map {
        transform: scale(6.2);
        transform-origin: top left;
    }
</style>

