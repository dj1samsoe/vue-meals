<template>
  <div class="bg-white shadow-md rounded-xl group relative transition-all">
    <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
      <div class="relative">
        <img
          :src="meal.strMealThumb"
          :alt="meal.strMeal"
          class="rounded-t-xl w-full h-48 object-cover"
        />
        <div
          className="flex gap-1 absolute top-0 left-0 w-full h-full bg-black opacity-0 transition-opacity duration-300 justify-center items-center text-white group-hover:opacity-80 rounded-t-xl text-sm font-medium"
        >
          <span>View Details</span>
        </div>
      </div>
    </router-link>
    <div class="flex justify-between items-center p-3">
      <h1 class="text-xl font-semibold">{{ meal.strMeal }}</h1>
      <YouTubeButton :href="meal.strYoutube" />
    </div>
  </div>
</template>

<script setup>
import YouTubeButton from "./YouTubeButton.vue";

const { meal } = defineProps({
  meal: {
    required: true,
    type: Object,
  },
});
</script>
