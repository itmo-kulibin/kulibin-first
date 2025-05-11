<script>
    import { base } from '$app/paths';

    export let text = '';
    export let customIcon = "point";
    export let customIconHeight = 64;
    export let posX = 0;
    export let posY = 0;
    export let onClick;

</script>

<div class="point-wrapper" style:top="{posY}px" style:left="{posX}px" on:click={onClick} >
    <img style:height="{customIconHeight}px" src="{base}/map/{customIcon}.svg" />
    <span>{text}</span>
</div>

<style>
    .point-wrapper {
        position: absolute;
        cursor: pointer;
        transform: translateX(-50%) translateY(-50%);
    }
    img {
        height: 64px;
        width: auto;
        max-width: unset;
    }
    span {
        display: block;
        width: 100%;
        text-align: center;
    }
</style>

