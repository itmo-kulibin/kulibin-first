<script>
    import { DEFAULT_PATHNAME } from "$lib/utils/default_pathname";

    export let tall = false;

    const links = [
        { name: "Биография", href: DEFAULT_PATHNAME + "biography" },
        //{ name: "Лифт изобретений", href: "/lift", isHighlighted: true },
        { name: "Кулибин-поэт", href: DEFAULT_PATHNAME + "poems" },
        //{ name: "Места в Петербурге", href: "/map" },
        { name: "Книга контактов", href: DEFAULT_PATHNAME + "contacts" },
        { name: "Изобретения", href: DEFAULT_PATHNAME + "article" },
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
