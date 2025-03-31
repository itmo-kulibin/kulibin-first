<script>
  import Contact from '../../../lib/components/Contact.svelte';

  let active1 = false;
  let active2 = false;
  let active3 = false;
</script>

<div style="position: absolute; left: 40%;">
    <Contact
    fullname="Иванов Иван Иванович"
    image="https://cdn-media.tass.ru/width/1020_b9261fa1/tass/m2/uploads/i/20200421/5495735.jpg"
    bind:isActive={active1}
    >
    Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
    publishing, and web development to fill empty spaces in a layout that does not yet have content.
    Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
    publishing, and web development to fill empty spaces in a layout that does not yet have content.
    Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
    publishing, and web development to fill empty spaces in a layout that does not yet have content.
    </Contact>

    <Contact
    fullname="Иванов Иван Иванович"
    image="https://cdn-media.tass.ru/width/1020_b9261fa1/tass/m2/uploads/i/20200421/5495735.jpg"
    bind:isActive={active2}
    >
    Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
    publishing, and web development to fill empty spaces in a layout that does not yet have content.
    </Contact>

    <Contact
    fullname="Иванов Иван Иванович"
    image="https://cdn-media.tass.ru/width/1020_b9261fa1/tass/m2/uploads/i/20200421/5495735.jpg"
    bind:isActive={active3}
    >
    Lorem ipsum is a dummy or placeholder text commonly used in graphic design,
    publishing, and web development to fill empty spaces in a layout that does not yet have content.
    </Contact>
</div>