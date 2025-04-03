<script>
  export let fullname = "";
  export let image = "";
  export let isActive = false;

  function contact_click(){ 
    isActive = !isActive;
  }

</script>

<div class="contact">

  <div>
    <a on:click={contact_click} class="contact-title" href="#">
      {fullname}
    </a>
  </div>

  <div class="contact-info-default" class:contact-info-active={isActive}>
    <hr>
    <div class="contact-info">
        <p>
          <img src={image} alt={fullname} class="image-class"/>
          <slot></slot>
        </p>
    </div>
  </div>

  <hr>

</div>

<style>
  .contact {
    display: block;
    width: 357px;
  }

  .contact-title {
    flex-grow: 1;
    font-size: 1.2em;
    margin: 10px;
  }

  .contact-info-default { 
    display: none;
  }

  .contact-info-active {
    display: inline;
  }

  .contact-info{
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

