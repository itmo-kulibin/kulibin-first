<script>

    import { base } from '$app/paths';

    export let fullname = "";
    export let image = "";
    export let isActive = false;

    function contact_click(){
    isActive = !isActive;
    }

</script>

<div class="contact">

  <div>
    <span on:click={contact_click} class="contact-title">
      {fullname}
    </span>
  </div>

  <div class="contact-info-default" class:contact-info-active={isActive}>
    <hr>
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
<hr>


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
    color:#fff;
    background-color:#fff;
    height:1px;
    width:100%;
  }
</style>

