<script>
    export let name = "Иван Петрович Кулибин";
    export let imageSrc = "/Images/portrait.png";
</script>

<div class="portrait-container">
    <img src={imageSrc} alt="Портрет {name}" class="portrait" />
    <div class="name-overlay">
        <h2>{name}</h2>
    </div>
</div>
<p class="bio-text">
    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
</p>

<style>
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