<template>
  <div class="w-full h-[60vh] bg-[url(./assets/hero.jpg)] bg-cover bg-center">
    <div class="w-full h-full flex justify-center items-center">
      <h1 class="text-5xl font-bold text-white">
        {{ title }}
      </h1>
    </div>
  </div>
</template>

<script setup>
const { title } = defineProps(["title"]);
</script>
