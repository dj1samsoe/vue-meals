<template>
  <Hero :title="title" />
  <div class="p-8 pb-5 text-neutral-900 flex justify-center">
    <h1 class="text-4xl font-bold mb-4">Random Meals</h1>
  </div>
  <Meals :meals="meals" />
</template>

<script setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import Meals from "../components/Meals.vue";
import axiosClient from "../axiosClient.js";
import Hero from "../components/Hero.vue";

const title = "Home";

const meals = ref([]);

onMounted(async () => {
  for (let i = 0; i < 6; i++) {
    axiosClient
      .get(`random.php`)
      .then(({ data }) => meals.value.push(data.meals[0]));
  }
});
</script>
