<template>
  <Hero :title="title" />
  <div class="p-8 pb-5">
    <h1 class="text-4xl font-bold mb-4 text-neutral-900 text-center">Search</h1>
  </div>
  <div class="flex flex-wrap justify-center gap-3 px-8 mb-10">
    <router-link
      :to="{ name: 'byLetter', params: { letter } }"
      v-for="letter of letters"
      :key="letter"
      class="w-2 h-2 flex items-center justify-center hover:text-neutral-500 hover:scale-150 transition-all"
    >
      {{ letter }}
    </router-link>
  </div>
  <Meals :meals="meals" />
</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, watch, ref } from "vue";
import { useRoute } from "vue-router";
import store from "../store";
import Meals from "../components/Meals.vue";
import Hero from "../components/Hero.vue";

const route = useRoute();
const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
const meals = computed(() => store.state.mealsByLetter);
const title = ref("");

watch(route, () => {
  store.dispatch("searchMealsByLetter", route.params.letter);
  title.value = "Meals by Letter : " + route.params.letter;
});

onMounted(() => {
  store.dispatch("searchMealsByLetter", route.params.letter);
  title.value = "Meals by Letter : " + route.params.letter;
});
</script>
