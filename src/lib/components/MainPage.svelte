<script>
    export let name = "Иван Петрович Кулибин";
    export let imageSrc = "/Images/portrait.png";
</script>
<nav class="navbar">
        <h1>Кулибин</h1>
        <svg class="menu-icon" width="52" height="52" viewBox="0 0 24 24" fill="none" stroke="currentColor">
            <path stroke-width="2" stroke-linecap="round" d="M3 12h18M3 6h18M3 18h18"/>
        </svg>
    </nav>
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
    }
        h2 {
        font-family: 'Montserrat', sans-serif;
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
    }
    
    .navbar {
        display: flex;
        justify-content: space-between;
        background-color: #000957;
        color: white;
    }

    .menu-icon {
        cursor: pointer;
        margin-top: 10px;
        margin-right: 10px;
    }
    
    h1 {
        font-family: 'Montserrat', sans-serif;
        font-size: 42px;
        font-weight: 700;
        margin-bottom: 40px;
        text-align: left;
    }


    @media (max-width: 700px) {
        .portrait-container {
            width: 100%;
            max-width: 100%;
            border-radius: 0;
            height: auto;
            margin: 0 0 10px 0;
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