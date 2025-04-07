<script>
    export let tall = false;

    const links = [
        { name: "Биография", href: "/biography" },
        //{ name: "Лифт изобретений", href: "/lift", isHighlighted: true },
        { name: "Кулибин-поэт", href: "/poems" },
        //{ name: "Места в Петербурге", href: "/map" },
        { name: "Книга контактов", href: "/contacts" },
        { name: "Изобретения", href: "/article" },
    ];
</script>

<nav class="w-full">
    <ul class="flex flex-col gap-2">
        {#each links as link}
            <li>
                <a
                        href={link.href}
                        class="block w-full px-6 rounded-lg font-medium text-base
                           text-white
                           text-right relative
                           {tall ? 'h-20 flex items-end justify-end pb-2' : 'h-14 flex items-center justify-end'}
                           {link.isHighlighted ? 'bg-[#ffae00]' : 'bg-[#344cb7]'}"
                >
                    {link.name} ➔
                </a>
            </li>
        {/each}
    </ul>
</nav>
