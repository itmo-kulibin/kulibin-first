<script>
  import Contact from "$lib/components/Contact.svelte";
  import ContactsFilters from "$lib/components/ContactsFilters.svelte";
  import { CONTACTS, FILTERS } from "$lib/content/contacts";
  import { getContext } from 'svelte';

  const filters = FILTERS;

  let activeFilter = $state();

  let contactsState = $state({});

  const custom = getContext('custom-page-props');
</script>

<div class="contacts-wrapper">
  <ContactsFilters {filters} bind:activeFilter />

  <ul class="contacts-card">
    <!-- Подразумевается, что список CONTACTS всегда непустой. -->
    {#each CONTACTS.filter((contact) => activeFilter === "all" || contact.tags?.includes(activeFilter)) as contact}
        <li on:click={(event) => {
            if (event.target.nodeName === "HR" || event.target.nodeName === "LI") return;
            for (let a in contactsState) {
                if (a != contact.name.replaceAll(" ", "_") + "__" + contact.text.length) {
                    contactsState[a] = false;
                }
            }
            
            if (contactsState[contact.name.replaceAll(" ", "_") + "__" + contact.text.length]) {
                event.target.closest("li").scrollIntoView({ block: 'start', behavior: 'instant' });
                setTimeout(() => { custom.hideHeader() }, 100);
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
    gap: 1rem;
    padding: 15px 0;
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

</style>

