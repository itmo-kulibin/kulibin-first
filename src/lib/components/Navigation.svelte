<script lang="ts">
    export let tall: boolean = false;

    const links = [
        { name: "Биография", href: "/biography" }, // !!! Нужно будет изменить, ссылка сделана для примера
        { name: "Лифт изобретений", href: "/inventions-elevator" }, // !!! Нужно будет изменить, ссылка сделана для примера
        { name: "Кулибин-поэт", href: "/poet" }, // !!! Нужно будет изменить, ссылка сделана для примера
        { name: "Места в Петербурге", href: "/petersburg-places" }, // !!! Нужно будет изменить, ссылка сделана для примера
        { name: "Книга контактов", href: "/contacts" }, // !!! Нужно будет изменить, ссылка сделана для примера
        { name: "Изобретения", href: "/inventions" }, // !!! Нужно будет изменить, ссылка сделана для примера
    ];
</script>

<nav class="w-full">
    <ul class="flex flex-col gap-2">
        {#each links as link}
            <li>
                <a
                        href={link.href}
                        class="block w-full px-6 rounded-lg font-medium text-base
                 bg-[#344cb7] hover:bg-[#ffae00] text-white
                 transition-all duration-200
                 text-right relative
                 {tall ? 'h-16 flex items-end justify-end pb-2' : 'py-3'}"
                >
                    {link.name} ➔
                </a>
            </li>
        {/each}
    </ul>
</nav>