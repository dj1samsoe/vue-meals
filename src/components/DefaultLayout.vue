<template>
  <navbar />
  <main>
    <div class="max-w-screen-2xl">
      <router-view />
    </div>
  </main>
</template>

<script setup>
import Navbar from "../components/Navbar.vue";
</script>
