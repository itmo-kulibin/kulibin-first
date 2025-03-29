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
        <div class="content-wrapper">
            {#if !isExpanded}
                <div class="short-text">
                    <slot name="short" />
                </div>
            {/if}
        
            {#if $$slots.full}
                <div class="full-text" class:is-expanded={isExpanded}>
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
	
    .content-wrapper {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .full-text {
        margin-top: 0.75rem;
        padding-top: 0.75rem;
        max-height: 0;
        overflow: hidden;
        opacity: 0;
        white-space: pre-line;
        transition: all 0.3s ease;
    }
    
    .short-text {
        white-space: pre-line;
    }

    .full-text.is-expanded {
        max-height: 1000px;
        opacity: 1;
        padding-top: 0.75rem;
        margin-top: 0.75rem;
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