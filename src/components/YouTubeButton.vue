<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded text-white bg-neutral-800 hover:bg-neutral-900 transition-colors"
  >
    <slot>YouTube</slot>
  </a>
</template>

<script setup>
const props = defineProps({
  href: String,
});
</script>
