<script>
  import Contact from '../../../lib/components/Contact.svelte';

  let active = false;
</script>

<Contact
  fullname="Иванов Иван Иванович"
  image="https://cdn-media.tass.ru/width/1020_b9261fa1/tass/m2/uploads/i/20200421/5495735.jpg"
  bind:active={active}
>
Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
publishing, and web development to fill empty spaces in a layout that does not yet have content.
</Contact>