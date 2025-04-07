<script>
    import MapPopup from '$lib/components/MapPopup.svelte';
    let active = true;
  
    function openPopup() {
      active = true;
    }
  </script>
  <button on:click={openPopup}>Открыть</button>
  
  
  <MapPopup 
    image="https://www.spbmuzei.ru/wp-content/uploads/2024/07/zimnij-dvorecz-s-karetami-scaled.jpg" 
    title="Зимний дворец" 
    yamaps="https://google.com"
    yamaps_addres="Дворцовая площадь, 2"
    bind:active={active}
  >
    <p>Презентация Кулибиным своего изобретения - электрофора.</p>
  </MapPopup>