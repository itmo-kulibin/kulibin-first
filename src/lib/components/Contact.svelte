<script>
  export let fullname = "";
  export let image = "";
  export let isActive = false;
  let contact_info_display = "none";

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
      <div class="image-container">
        <img src={image} alt={fullname} />
      </div>
      <div class='contact-text'>
        <p>
          <slot></slot>
        </p>
      </div>
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
  }

  .contact-text{
    flex: 1.9;
  }

  .contact-text p{
    color: black;
    margin-left: 5px;
    font-size: 1em;
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

  .image-container {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .image-container img {
    width: 100%;
    height: auto;
    border-radius: 5%;
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

