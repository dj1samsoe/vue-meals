<template>
  <header
    class="bg-white shadow-md h-16 fixed w-full z-50 flex justify-between items-stretch px-8"
  >
    <h1 class="flex items-center text-3xl font-bold">
      Meals <span class="text-neutral-500">Vue.js</span>
    </h1>
    <div class="flex items-center gap-1">
      <router-link
        :to="{ name: 'home' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-neutral-500 hover:text-white"
      >
        Home
      </router-link>
      <router-link
        :to="{ name: 'byName' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-neutral-500 hover:text-white"
      >
        Search Meals
      </router-link>
      <router-link
        :to="{ name: 'byLetter' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-neutral-500 hover:text-white"
      >
        Meals By Letter
      </router-link>
      <router-link
        :to="{ name: 'ingredients' }"
        class="inline-flex items-center px-2 h-full transition-colors hover:bg-neutral-500 hover:text-white"
      >
        Meals By Ingredients
      </router-link>
    </div>
  </header>
</template>
