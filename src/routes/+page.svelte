<script>
    import Navigation from '$lib/components/Navigation.svelte';
    import { base } from '$app/paths';
</script>

<main class="main-content">
    <div class="main">
        <div class="portrait-container">
            <img src="{base}/images/portrait.png" alt="Портрет Иван Петрович Кулибин" class="portrait" />
            <div class="name-overlay">
                <h2>Иван Петрович Кулибин</h2>
            </div>
        </div>
        <p class="bio-text">
            Гений-самоучка, опередивший своё время, — Иван Кулибин создавал удивительные механизмы, которые могли бы изменить мир. Узнайте, как изобретатель без академического образования стал символом русской инженерной мысли!
        </p>
    </div>
    <div class="nav">
        <Navigation />
    </div>
</main>

<style>
    .main-content {
        margin: 0 auto;
        text-align: center;
        background: #000957;
        color: #fff2f2;
        padding: 20px;
    }
    .nav{
        margin: 0 auto;
        max-width: 600px;
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

    .portrait-container {
        position: relative;
        width: 400px;
        height: 600px;
        margin: 0 auto 30px auto;
        overflow: hidden;
        box-shadow: 0 0px 20px #00095700;
    }
    .bio-text {
        font-size: 20px;
        max-width: 100%;
        margin-bottom: 20px;
        padding: 20px;
    }
    h2 {
        font-size: 42px;
        font-weight: 600;
        margin: 0;
    }
    .portrait {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .name-overlay {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        height: 60%;
        background: linear-gradient(180deg, #00095700, #000957);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: flex-end;
        box-sizing: border-box;
        padding: 10px
    }

    @media (max-width: 700px) {
        .portrait-container {
            width: 100%;
            height: auto;
        }

        .portrait {
            width: 100%;
            height: auto;
            aspect-ratio: 3/4;
        }

        .name-overlay {
            height: 50%;
        }
    }

</style>
