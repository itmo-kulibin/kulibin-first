<script>
    import Map from '$lib/components/Map.svelte';

    let points = $state([]);
    let last = $state();
    let n = 0;
</script>

<div on:click={(e)=>{
     if (!e.target.classList.contains("map")) return;

     n++;
     points.push({posX: last.x, posY: last.y, text: ""+n});

     console.log("Current points: ", $state.snapshot(points));
     console.log(e.target.width, e.target.height);
    }}>
<Map bind:lastClicked={last} bind:points={points} />
</div>

