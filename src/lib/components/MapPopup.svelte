<script>
  import { fade } from "svelte/transition";
  import Quiz from './Quiz.svelte'; // Make sure to import your Quiz component
  import EmbeddedBlock from './EmbeddedBlock.svelte'; // Import your EmbeddedBlock components
  import EmbeddedBlockText from './EmbeddedBlockText.svelte';

  export let data = {}; // This will receive the entire data object
  export let active = false;

  function closePopup() {
    active = false;
  }

  $: paragraphs = data.text ? data.text.split('\n').filter(p => p.trim() !== '') : [];
</script>

{#if active}
  <div class="popup-overlay" transition:fade={{ duration: 100 }}>
    <div class="popup">
      <button class="close-btn" on:click={closePopup}>
        <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g clip-path="url(#clip0_178_307)">
            <rect x="4" y="4" width="40" height="40" rx="20" fill="#344CB7"/>
            <path d="M18.4 31L17 29.6L22.6 24L17 18.4L18.4 17L24 22.6L29.6 17L31 18.4L25.4 24L31 29.6L29.6 31L24 25.4L18.4 31Z" fill="#FFF2F2"/>
          </g>
          <defs>
            <clipPath id="clip0_178_307">
              <rect x="4" y="4" width="40" height="40" rx="20" fill="white"/>
            </clipPath>
          </defs>
        </svg>
      </button>

      <!-- Main content -->
      <h1><b>{data.name}</b></h1>

      <!-- Image if available -->
      {#if data.image}
        <img src={data.image} alt={data.name} class="popup-image" />
      {/if}

      <!-- Main text -->
      {#each paragraphs as paragraph}
        <p>{paragraph}</p>
      {/each}

      <!-- Fact section -->
      {#if data.fact}
        <EmbeddedBlock title="Любопытный факт">
          <EmbeddedBlockText slot="full">
            {data.fact}
          </EmbeddedBlockText>
        </EmbeddedBlock>
      {/if}

      <!-- Quiz section -->
      {#if data.quiz}
        <div class="question">
          <Quiz data={data.quiz}/>
        </div>
      {/if}
    </div>
  </div>
{/if}

<style>
  .popup-overlay {
    top: 74px; /* высота хедера */
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 9, 87, 0.2);
    align-items: center;
    justify-content: center;
    display: flex;
    position: absolute;
    margin-top: 10px;
    z-index: 1000;
  }

  .popup {
    background: #FFF2F2;
    padding: 20px;
    border-radius: 10px;
    width: calc(100% - 40px);
    height: calc(100% - 40px);
    max-width: 500px;
    max-height: 90vh;
    text-align: center;
    position: relative;
    box-sizing: border-box;
    overflow-y: auto;
  }

  .popup h1 {
    font-size: 24px;
    margin: 10px 0 20px;
    color: #000;
  }

  .popup-image {
    max-height: 200px;
    width: auto;
    max-width: 100%;
    border-radius: 10px;
    margin-bottom: 20px;
  }

  .popup p {
    text-align: left;
    margin-bottom: 20px;
    line-height: 1.5;
  }

  .close-btn {
    position: absolute;
    top: 10px;
    right: 10px;
    background: none;
    border: none;
    cursor: pointer;
    z-index: 10;
  }

  .map-link {
    display: inline-block;
    margin: 20px 0 10px;
    color: blue;
    padding: 10px 20px;
    text-decoration: none;
    border: 1px solid blue;
    border-radius: 5px;
  }

  .question {
    margin: 20px 0;
  }
</style>
