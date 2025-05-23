<script>
    import '../app.css';
    
    import { page } from "$app/state";
    import { base } from "$app/paths";
    import { onMount, setContext } from 'svelte';
    import { fade } from 'svelte/transition';
    import Navigation from "$lib/components/Navigation.svelte";

    const MOBILE_RES_W = 768;

    let { children } = $props();

    let innerWidth = $state(0);
    let innerHeight = $state(0);
    let iframe = $state();
    let window = $state();
    let menuExtended = $state(false);

    // Переменные для shy header
    let header = $state(null);
    let headerHeight = $state(84); // Изначальная высота заголовка из стилей
    let headerShifterHeight = $state(0);
    let lastScrollY = $state(0);
    let isHeaderVisible = $state(true);

    const customPageProps = {
        hideHeader: () => {
            isHeaderVisible = false;
        }
    };
    setContext('custom-page-props', customPageProps);

    function handleScroll() {
        if (innerWidth <= MOBILE_RES_W) {
            const currentScrollY = window.scrollY;
            
            // Скрыть при прокрутке вниз, показать при прокрутке вверх
            if (currentScrollY > lastScrollY && currentScrollY > headerHeight) {
                isHeaderVisible = false;
            } else {
                isHeaderVisible = true;
            }
            
            lastScrollY = currentScrollY;
        }
    }

    onMount(() => {
        if (innerWidth > MOBILE_RES_W) {
            if (window.location.pathname != "/") {
                // TODO:
                //console.log("redirected");
                //window.location.pathname = "/";
            }
        }
        
        // Инициализация shy header
        if (header) {
            handleScroll(); // Установить начальное состояние
        }
    });

    let pageElement;
    const scrollToTop = () => {
        if (pageElement) {
            pageElement.scrollIntoView({
                behavior: 'smooth'
            });
        }
    };
</script>

<svelte:window bind:this={window} bind:innerWidth bind:innerHeight on:scroll={handleScroll} />

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
    <header 
        bind:this={header} 
        class="header" 
        class:header-hidden={!isHeaderVisible}
    >
    <a class="title" href="{base}/" on:click={() => {menuExtended = false}}>Кулибин</a>
        <button on:click={() => {menuExtended = !menuExtended;}} class="hamburger-button" aria-label="Открыть меню">
            <svg width="60" height="60" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M5 30V26.6667H35V30H5ZM5 21.6667V18.3333H35V21.6667H5ZM5 13.3333V10H35V13.3333H5Z" fill="#FFF2F2"/>
            </svg>
        </button>
    </header>
    {#if menuExtended}
        <div class="hamburger-menu" transition:fade on:click={() => {menuExtended = false}}>
            <Navigation />
        </div>
    {/if}
    <div class="page" bind:this={pageElement}>
        {@render children()}

        <div class="go-top" class:hidden={!isHeaderVisible} on:click={scrollToTop}>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" stroke="currentColor" stroke-width="2"
                 stroke-linecap="round" stroke-linejoin="round" class="feather feather-arrow-up">
              <line x1="12" y1="19" x2="12" y2="5" />
              <polyline points="5 12 12 5 19 12" />
            </svg>
        </div>
    </div>
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
        height: 100vh;
        max-height: 1000px;
        overflow: auto;
        border: 2px solid #c4c4c4;
        border-top: none;
        border-bottom: none;
    }

    .header {
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        background-color: #000957;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 5px 15px;
        z-index: 1001;
        height: 84px;
        transform: translateY(0);
        transition: transform 0.3s ease-in-out;
    }
    
    .header-hidden {
        transform: translateY(-100%);
    }
    
    .header .title {
        font-size: 54px;
        color: #FFF2F2;
        font-weight: bold;
    }

    .hamburger-menu {
        position: fixed;
        left: 0;
        bottom: 0;
        right: 0;
        background-color: #000957;
        height: 100%;
        z-index: 1000;
        top: 84px;
        padding: 20px 20px;
    }

    .page {
        padding-top: 84px;
    }

    .go-top {
        position: fixed;
        right: 10px;
        bottom: 10px;
        background-color: #000957;
        width: 48px;
        height: 48px;
        color: #FFF2F2;
        border-radius: 5px;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        transform: translateX(0);
        transition: transform 0.3s ease-in-out;

    }

    .go-top.hidden {
        transform: translateX(200%);
    }


    @media screen and (max-width: 375px) {
        .header .title {
            font-size: 48px;
        }
    }
    @media screen and (max-width: 340px) {
        .header .title {
            font-size: 42px;
        }
    }
</style>
