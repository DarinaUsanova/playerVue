<script setup>
import { ref } from 'vue'

const isfavorite = ref(false)
const toggleFavorite = () => {
  isfavorite.value = !isfavorite.value
}
</script>

<template>
  <nav class="flex justify-between mb-7">
    <button @click="toggleFavorite" class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="rounded-full w-10 h-10 flex items-center justify-center leading-10 bg-white text-[#f53192] shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-transform hover:scale-110"
      >
        <img
          :src="isfavorite ? '/heart-solid.svg' : '/heart-regular.svg'"
          alt="heart icon"
          class="w-6 h-6"
        />
      </div>
    </button>
    <button class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="rounded-full w-10 h-10 flex items-center justify-center leading-10 bg-white text-[#f53192] shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-transform hover:scale-110"
      >
        <img src="/bars-solid.svg" alt="bars icon" class="w-6 h-6" />
      </div>
    </button>
  </nav>
</template>
