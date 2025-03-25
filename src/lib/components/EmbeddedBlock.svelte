<script>
    export let title = '';
    let isExpanded = false;
  
    function toggleExpand() {
        isExpanded = !isExpanded;
    }
</script>

<div class="embedded-block">
    {#if title}
        <h3 class="embedded-block__title">{title}</h3>
    {/if}
    
    <div class="embedded-block__content">
        <slot name="short" />
        
        {#if $$slots.full}
            <div class="full-text" class:is-hidden={!isExpanded}>
                <slot name="full" />
            </div>
            
            <div class="toggle-container">
                <button 
                    class="embedded-block__toggle" 
                    on:click={toggleExpand}
                    aria-expanded={isExpanded}
                >
                    <span class="arrow">{isExpanded ? '⌃' : '⌄'}</span>
                </button>
            </div>
        {/if}
    </div>
</div>

<style>
	  .embedded-block {
        padding: 1rem;
        margin: 1.5rem 0;
        background: #98a5d8;
			  color: #42487c;
        font-family: serif;
        line-height: 1.6;
    }

	  .embedded-block__title {
        margin: 0 0 0.5rem 0;
        font-size: 1.25rem;
        font-weight: 600;
        color: #1f2937;
    }
	
    .full-text {
        margin-top: 0.75rem;
        padding-top: 0.75rem;
        transition: all 0.3s ease;
        overflow: hidden;
    }
    
    .full-text.is-hidden {
        max-height: 0;
        opacity: 0;
        padding-top: 0;
        margin-top: 0;
        border-top: none;
    }
    
    .toggle-container {
        display: flex;
        justify-content: center;
        width: 100%;
        margin-top: 0.5rem;
    }
    
    .embedded-block__toggle {
        display: flex;
        align-items: center;
        justify-content: center;
        color: #1f2937;
        cursor: pointer;
			  background: none;
			  border: none;
        font-size: 1.6rem;
        font-family: sans-serif;
        transition: all 0.2s ease;
        width: auto;
    }
</style>