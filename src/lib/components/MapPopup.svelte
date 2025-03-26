<script>
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
    <div class="popup-overlay">
      <div class="popup">
        <button class="close-btn" on:click={closePopup}><svg width="25" height="25" viewBox="0 0 100 100">
          <circle cx="50" cy="50" r="50" fill="rgba(0, 9, 87, 1)"/>
          <line x1="30" y1="30" x2="70" y2="70" stroke="white" stroke-width="5"/>
          <line x1="30" y1="70" x2="70" y2="30" stroke="white" stroke-width="5"/>
        </svg></button>
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
      background: rgba(0, 9, 87, 1);
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
      width: 100%;
      border-radius: 10px;
    }
  
    .close-btn {
      position: absolute;
      top: 10px;
      right: 10px;
      background: none;
      border: none;
      font-size: 24px;
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
      border-radius: 5px;
      
      display: inline-block;
      width: max-content;
      text-align: center;
    }
  </style>
  