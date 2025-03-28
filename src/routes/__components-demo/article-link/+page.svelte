<script>
    import ArticleLink from '$lib/components/ArticleLink.svelte';
  
    let links = [
      { text: 'Часы', pagename: 'clock' },
      { text: 'Мост', pagename: 'bridge' },
      { text: 'Фонарь', pagename: 'lantern' },
      { text: 'Фейерверк', pagename: 'firework' },
      { text: 'Судно', pagename: 'ship' },
      { text: 'Лифт', pagename: 'elevator' },
      { text: 'Самокатка', pagename: 'scooter' },
      { text: 'Протез', pagename: 'prosthesis' },
      { text: 'Телеграф', pagename: 'telegraph' }
    ];
  </script>
  
  <h1>Демо: ArticleLink</h1>
  
  <div class="article-list">
    {#each links as { text, pagename }}
      <ArticleLink {text} {pagename} />
    {/each}
  </div>
  