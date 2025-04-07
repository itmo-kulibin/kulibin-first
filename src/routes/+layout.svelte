<script>
    import '../app.css';
    
    import { page } from "$app/state";
    import { onMount } from 'svelte';


    const MOBILE_RES_W = 768;

    let { children } = $props();

    let innerWidth = $state(0);
    let innerHeight = $state(0);
    let iframe = $state();
    let window = $state();

    onMount(() => {
        if (innerWidth > MOBILE_RES_W) {
            if (window.location.pathname != "/") {
                // TODO:
                //console.log("redirected");
                //window.location.pathname = "/";
            }
        }
    });
</script>

<svelte:window bind:this={window} bind:innerWidth bind:innerHeight />

 {#if innerHeight < 600}
    <div class="vertical-warn">
        <p>Окно слишком маленькое по высоте!</p>
        <p>Если вы используете телефон, переверните его в вертикальное положение.</p>
    </div>
 {:else if innerWidth > MOBILE_RES_W}
        <div class="view-wrapper">
            <div class="view">
                <iframe
                        bind:this={iframe}
                        width="100%"
                        height="100%"
                        src="{page.url.href}"
                    >
                </iframe>
            </div>
        </div>
{:else}
    {@render children()}
{/if}

<style>
    .vertical-warn {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
            
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .view-wrapper {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .view {
        position: relative;
        width: 500px;
        height: 90vh;
        max-height: 1000px;
        border-radius: 10px;
        overflow: scroll;
        border: 3px solid #c4c4c4;
    }
</style>

