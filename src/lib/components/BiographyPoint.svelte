<script>
  export let year = '';
</script>

<div class="relative w-full mb-5 font-[Inter]">
  <div class="flex items-center">
      <div class="w-16 h-16 border-4 border-[#000957] rounded-full mr-5"></div>
      <div class="text-6xl font-bold text-[#344CB7]">{year}</div>
  </div>
  <div class="relative pl-16 text-[#000957] text-lg">
      <div class="absolute left-7 top-0 bottom-0 w-1 bg-[#000957]"></div>
      <slot></slot>
  </div>
</div>