<script>
    import MainPage from '$lib/components/MainPage.svelte';
    import Navigation from '$lib/components/Navigation.svelte';
</script>

<main class="main-content">
    <div class = "main">
    <MainPage />
    </div>
    <div class = "nav">
    <Navigation />
    </div>
</main>

<style>

    .main-content {
        max-width: 1205px;
        margin: 0 auto;
        text-align: center;
        background: #000957;
        color: #fff2f2;
        padding: 20px;

    }
    
    .main {
        margin-left: -20px;
        margin-right: -20px;
    }
    @media (max-width: 700px) {
        h1 {
            margin-left: 15px;
        }
        .bio-text {
            padding: 10px 15px;
            font-size: 15px;
        }
    }
</style>