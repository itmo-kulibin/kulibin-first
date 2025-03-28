<script>
    import { fade } from "svelte/transition";
    export let image = "";
    export let title = "";
    export let yamaps = "";
    export let yamaps_addres = "";
    export let active = false;
    

    function closePopup() {
      active = false;
    }
  </script>
  
  {#if active}
    <div class="popup-overlay" transition:fade={{ duration: 100 }}>
      <div class="popup">
        <button class="close-btn" on:click={closePopup}><svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g clip-path="url(#clip0_178_307)">
          <rect x="4" y="4" width="40" height="40" rx="20" fill="#344CB7"/>
          <path d="M18.4 31L17 29.6L22.6 24L17 18.4L18.4 17L24 22.6L29.6 17L31 18.4L25.4 24L31 29.6L29.6 31L24 25.4L18.4 31Z" fill="#FFF2F2"/>
          </g><defs><clipPath id="clip0_178_307">
          <rect x="4" y="4" width="40" height="40" rx="20" fill="white"/>
          </clipPath></defs></svg>
        </button>
        <img src={image} alt={title} class="popup-image" />
        <h1><b>{title}</b></h1>
        <slot></slot>
        <a href={yamaps} target="_blank" class="map-link">📍Посмотреть на карте<br>{yamaps_addres}</a>
      </div>
    </div>
  {/if}
  
  <style>
    .popup-overlay {
      position: fixed;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 9, 87, 0.2);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .popup {
      background: white;
      padding: 10px;
      border-radius: 10px;
      width: 95dvw;
      height: 97dvh;
      max-width: 500px;
      text-align: center;
      position: relative;
    }
  
    .popup h1 {
      font-size: 40px;
      margin: 5px 0;
      color: #000;
    }

    .popup-image {
      max-height: 400px;
      width: 100%;
      border-radius: 10px;
    }
  
    .close-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: none;
      border: none;
      cursor: pointer;
    }
  
    .map-link {
      position: absolute;
      bottom: 0px;
      left: 50%;
      transform: translateX(-50%);
      color: blue;
      padding: 10px 20px;
      text-decoration: none;
      
      display: inline-block;
      width: max-content;
      text-align: center;
    }
  </style>
  