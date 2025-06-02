<script>

    import { base } from '$app/paths';
    import { FILTERS } from "$lib/content/contacts";


    export let fullname = "";
    export let image = "";
    export let isActive = false;
    export let tags = [];

    function contact_click(){
    isActive = !isActive;
    }

</script>

<div class="contact">

  <div on:click={contact_click}>
    <span class="contact-title">
      {fullname}
    </span>
    <span class="contact-tags">
      {#each tags as tag, i}
        <span class="tag tag-{tag}">{FILTERS[tag].text}</span>
      {/each}
    </span>
  </div>

  <div class="contact-info-default" class:contact-info-active={isActive}>
    <hr/>
    <div class="contact-info">
        <p>
            {#if image}
                <img src="{base}/images/c/{image}" alt={fullname} class="image-class"/>
            {/if}
          <slot></slot>
        </p>
    </div>
  </div>
</div>
<hr />


<style>
  .contact {
    display: block;
    width: 357px;

    margin: 5px auto;
  }

  .contact-title {
    flex-grow: 1;
    font-size: 1.2em;
    margin: 5px;
    width: 100%;
    display: block;
    cursor: pointer;
  }

  .contact-info-default {
    display: none;
  }

  .contact-info-active {
    display: inline;
  }

  .contact-info{
    padding: 3px;
    display: flex;
  }

  .image-class{
    width: 40%;
    margin: 7px;
    height: auto;
    border-radius: 5%;
    float: left;
  }

  hr {
    border:none;
    border-top:1.5px dotted black;
    background-color:#fff;
    height:1px;
    width:100%;
  }

  .contact-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 4px;
  }

  .tag {
      padding: 2px 6px;
      border-radius: 4px;
      font-size: 12px;
      font-weight: 500;
      text-transform: uppercase;
      letter-spacing: 0.03em;
  }

  a {
      color: #0066cc; /* Синий, как у стандартных ссылок */
      text-decoration: underline;
  }
  a:hover {
      color: #004499; /* Темно-синий при наведении */
  }

  /* Примеры цветов для тегов (аналоги Telegram) */
  .tag-favorite { background-color: #fed78a; color: #bd9146; }
  .tag-relatives { background-color: #f4a060; color: #a15821; }
  .tag-apprentices { background-color: #d8c0a6; color: #af986e; }
  .tag-scientists { background-color: #7ea4c8; color: #3d5674; }
  .tag-customers { background-color: #d8c0a6; color: #9b6f4c; }
  .tag-officials { background-color: #9b6f4c; color: #533721; }
  .tag-foreigners { background-color: #afc7f7; color: #5c74a4; }
  .tag-other { background-color: #e5e0da; color: #9a958f; }
</style>

