<script>
  import Contact from "$lib/components/Contact.svelte";
  import ContactsFilters from "$lib/components/ContactsFilters.svelte";
  import { CONTACTS, FILTERS } from "$lib/content/contacts";

  const filters = FILTERS;

  let activeFilter = $state();

  let contactsState = $state({});
</script>

<div class="contacts-wrapper">
  <ContactsFilters {filters} bind:activeFilter />

  <ul class="contacts-card">
    <!-- Подразумевается, что список CONTACTS всегда непустой. -->
    {#each CONTACTS.filter((contact) => activeFilter === "all" || contact.tags?.includes(activeFilter)) as contact}
        <li on:click={() => {
            for (let a in contactsState) {
                if (a != contact.name.replaceAll(" ", "_") + "__" + contact.text.length) {
                    contactsState[a] = false;
                }
            }
        }}>
          <Contact
                  fullname={contact.name}
                  image={contact.image}
                  bind:isActive={contactsState[contact.name.replaceAll(" ", "_") + "__" + contact.text.length]}>
            {contact.text}
          </Contact>
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
    display: flex;
    flex-direction: column;
    align-items: center;
  }


  @media screen and (max-width: 424px) {
    .contacts-wrapper {
        padding: 1rem 0.5rem;
    }
  }

</style>

