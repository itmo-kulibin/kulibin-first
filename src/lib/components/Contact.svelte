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
  .tag-favorite { background-color: #f3af32; color: #a37015; }
  .tag-relatives { background-color: #a15b28; color: #582f13; }
  .tag-apprentices { background-color: #e1d1b7; color: #bba687; }
  .tag-scientists { background-color: #405874; color: #162137; }
  .tag-customers { background-color: #97856f; color: #56442e; }
  .tag-officials { background-color: #564334; color: #261c13; }
  .tag-foreigners { background-color: #5e76a2; color: #324160; }
  .tag-other { background-color: #b8b3b0; color: #7b7670; }
</style>

