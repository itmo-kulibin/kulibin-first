<script>
    export let className;
  </script>
  
  <div class="embedded-block-text {className}">
    <slot />
  </div>

  <style>
    .embedded-block-text {
      display: block;
      white-space: pre-line;
    }
  </style>