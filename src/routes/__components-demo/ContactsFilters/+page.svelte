<script>
  import ContactsFilters from "$lib/components/ContactsFilters.svelte";

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
  };

  let active = $state();
</script>

<ContactsFilters {filters} bind:activeFilter={active} />
<h1>Текущий выбор: {active}</h1>
