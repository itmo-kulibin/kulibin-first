<script>
  export let filters;
  export let activeFilter;

  // Инициализация активного фильтра при монтировании
  $: {
    if (activeFilter === undefined) {
      const defaultKey = Object.keys(filters).find(
        (key) => filters[key].default,
      );
      activeFilter = defaultKey || Object.keys(filters)[0];
    }
  }
</script>

<div class="filters-container">
  {#each Object.keys(filters) as filterKey (filterKey)}
    <button
      class="filter-btn {activeFilter === filterKey ? 'active' : ''}"
      on:click={() => (activeFilter = filterKey)}
    >
      {filters[filterKey].text}
    </button>
  {/each}
</div>

<style>
  .filters-container {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .filter-btn {
    padding: 8px 16px;
    border-radius: 20px;
    border: 1px solid #344cb7;
    background: #f8f9fa;
    cursor: pointer;
    transition: all 0.2s;
    font-size: 14px;
  }

  .filter-btn:hover {
    background: #e9ecef;
  }

  .filter-btn.active {
    background: #b9b4b4;
    border-color: #344cb7;
  }
  
  @media screen and (max-width: 424px) {
      .filter-btn {
          padding: 6px 12px;
    }
  }
</style>
