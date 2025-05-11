<script>
    import Map from '$lib/components/Map.svelte';

    let points = $state([]);
    let last = $state();
    let n = 0;
</script>

<div on:click={()=>{
     n++;
     points.push({posX: last.x, posY: last.y, text: ""+n});

     console.log("Current points: ", $state.snapshot(points));
    }}>
<Map bind:lastClicked={last} bind:points={points} />
</div>

