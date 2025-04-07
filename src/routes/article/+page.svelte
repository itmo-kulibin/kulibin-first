<script>
    import ArticleLink from '$lib/components/ArticleLink.svelte';
    let links = [
      { text: 'Часы', pagename: 'article/egg-shaped-watch' },
      { text: 'Мост', pagename: 'article/bridge' },
      { text: 'Фонарь', pagename: 'article/lantern' },
      { text: 'Фейерверк', pagename: 'article/firework' },
      { text: 'Судно', pagename: 'article/boat' },
      { text: 'Лифт', pagename: 'article/elevator' },
      { text: 'Самокатка', pagename: 'article/samokatka' },
      { text: 'Протез', pagename: 'article/prosthetic-leg' },
      { text: 'Телеграф', pagename: 'article/telegraph' }
    ];
</script>

<div class="container">
    <h1><b>Изобретения Кулибина</b></h1>
    <div class="article-list">
        {#each links as { text, pagename }}
          <ArticleLink {text} {pagename} />
        {/each}
      </div>
</div>

<style>
    .container {
        margin: 0;
        padding: 0;

        justify-content: center;
        align-items: center;
        height: 100vh;

        padding: 20px;
        width: 100%;
    }

    h1 {
        font-size: 50px;
        color: #000957;
        text-align: center;
        line-height: 1.1;
    }
</style>