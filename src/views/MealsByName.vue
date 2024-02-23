<template>
  <Hero :title="title" />
  <div class="p-8 pb-0">
    <h1 class="text-4xl font-bold mb-4 text-neutral-900 text-center">Search</h1>
  </div>
  <div class="px-8 pb-10 flex justify-center">
    <input
      type="text"
      v-model="keyword"
      class="rounded border-2 bg-white border-gray-200 focus:ring-neutral-500 focus:border-neutral-500 w-full max-w-[500px]"
      placeholder="Search for Meals"
      @change="searchMeals"
    />
  </div>

  <Meals :meals="meals" />
</template>

<script setup>
import { computed } from "@vue/reactivity";
import { onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import store from "../store";
import Meals from "../components/Meals.vue";
import Hero from "../components/Hero.vue";

const route = useRoute();
const keyword = ref("");
const meals = computed(() => store.state.searchedMeals);
const title = ref("Meals by Name");

function searchMeals() {
  if (keyword.value) {
    store.dispatch("searchMeals", keyword.value);
    title.value = "Meals by Name : " + keyword.value;
  } else {
    store.commit("setSearchedMeals", []);
    title.value = "Meals by Name";
  }
}

onMounted(() => {
  keyword.value = route.params.name;
  if (keyword.value) {
    searchMeals();
  }
});
</script>
