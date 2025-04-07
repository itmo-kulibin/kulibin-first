<script>
  import ContactsFilters from "$lib/components/ContactsFilters.svelte";
  import { CONTACTS, CONTACTS } from "$lib/content/contacts";

  const filters = {
    all: {
      text: "Все",
      default: true,
    },
    scientists: {
      text: "Ученые",
    },
    students: {
      text: "Студенты",
    },
    friends: {
      text: "Друзья",
    },
  };

  let activeFilter = $state();
</script>

<div class="contacts-wrapper">
  <ContactsFilters {filters} bind:activeFilter />

  <ul class="contacts-card">
    <!-- Подразумевается, что список CONTACTS всегда непустой. -->
    {#each CONTACTS.filter((contact) => activeFilter === "all" || contact.tags?.includes(activeFilter)) as contact}
      <li>
        <span class="contact-name">{contact.name}</span>
        {#if contact.image || contact.text}
          <div class="contact-body">
            {#if contact.image}
              <img
                class="contact-image"
                src="images/contacts/{contact.image}"
                alt=""
              />
            {/if}
            {#if contact.text}
              <p class="contact-text">{contact.text}</p>
            {/if}
          </div>
        {/if}
      </li>
    {/each}
  </ul>
</div>

<style>
  .contacts-wrapper {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 2rem;
    gap: 1rem;
  }

  .contacts-card {
    background-color: white;
    border-radius: 12px;
    padding: 1rem;
    width: 100%;
    max-width: 640px;
  }

  .contact-name {
    font-size: 1.5rem;
    display: block;
    padding: 0.5rem;
    margin-bottom: 0.5rem;
    border-bottom: 1px dotted #000;
  }

  .contact-body {
    display: flex;
    gap: 0.75rem;
    border-bottom: 1px dotted #000;
  }

  .contact-image {
    width: 116px;
    height: auto;
    object-fit: cover;
  }

  .contact-text {
    font-size: 0.9rem;
    line-height: 1.4;
  }
</style>
