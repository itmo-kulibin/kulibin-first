<script>
  import { onMount, afterUpdate } from 'svelte';

  export let slides = [];


  let currentIndex = 0;
  let slider;
  let touchStartX = 0;
  let isDragging = false;
  let slideWidth;

  onMount(() => {
    slideWidth = slider.offsetWidth;
  });

  afterUpdate(() => {
    if (slider) {
      slideWidth = slider.offsetWidth;
    }
  });

  function goToSlide(index) {
    if (index < 0) index = slides.length - 1;
    if (index >= slides.length) index = 0;
    currentIndex = index;
  }

  function nextSlide() {
    goToSlide(currentIndex + 1);
  }

  function prevSlide() {
    goToSlide(currentIndex - 1);
  }

  function handleTouchStart(event) {
    touchStartX = event.touches[0].clientX;
    isDragging = true;
  }

  function handleTouchEnd(event) {
    if (!isDragging) return;
    isDragging = false;

    const touchEndX = event.changedTouches[0].clientX;
    const diff = touchEndX - touchStartX;

    if (diff > slideWidth / 4) {
      prevSlide();
    } else if (diff < -slideWidth / 4) {
      nextSlide();
    }
  }
</script>

<div class="slider-wrapper">
  <div
    class="slider"
    bind:this={slider}
    on:touchstart={handleTouchStart}
    on:touchend={handleTouchEnd}
    style="transform: translateX(-{currentIndex * 100}%);"
  >
    {#each slides as slide}
      <div class="slide">
      {#if slide.title}
        <h2 class="slide-title">{slide.title}</h2>
      {/if}

      {#if slide.text}
         {@html slide.text}
      {/if}

      {#if slide.images?.length > 0}
    <div class="slide-images">
      {#each slide.images as img}
        <img src={img} alt="Изображение" />
      {/each}
    </div>
  {/if}
    </div>
    {/each}
  </div>
  <button class="nav prev" on:click={prevSlide} aria-label="Предыдущий слайд">&#10094;</button>
  <button class="nav next" on:click={nextSlide} aria-label="Следующий слайд">&#10095;</button>
</div>

<style>
  .slider-wrapper {
    max-width: 100%;
    margin: 0 auto;
    user-select: none;
    position: relative;
    font-family: Arial, sans-serif;
  }

  .slider {
  display: flex;
  transition: transform 0.3s ease;
  width: 100%;
  }

    .slide {
    min-width: 100%;
    background: #a3b1f7;
    border-radius: 12px;
    padding: 10px;
    color: #2c2c54;
    font-size: 0.9rem;
    line-height: 1.4;
    user-select: text;
    word-break: break-word;
    border: 6px solid #fff4f4;
    }

    .slide-title {
  font-size: 1.8rem;
  font-weight: 600;
  margin-bottom: 0.8rem;
  color: #1a1a4d;
}

.slide-text {
  margin-bottom: 1.1rem;
}

.slide-images {
  max-width: 100%;
  display: flex;
  flex-direction: column;
  height: auto;
  border-radius: 8px;
  gap: 10px;
  flex-wrap: wrap;
  margin-top: 1rem;
}

  .nav {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: transparent;
    border: none;
    font-size: 1.8rem;
    color: #2c2c54;
    cursor: pointer;
    padding: 0 0.3rem;
    user-select: none;
  }

  .nav.prev {
    left: -10px;
  }

  .nav.next {
    right: -10px;
  }

  .nav:focus {
    outline: 2px solid #2c2c54;
    outline-offset: 2px;
  }
</style>
