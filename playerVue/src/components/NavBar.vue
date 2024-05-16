<script setup>
import { ref } from 'vue'

const isfavorite = ref(false)

const emits = defineEmits(['openFavorite'])

const toggleFavorite = () => {
  isfavorite.value = !isfavorite.value
}

const toggleFavoriteMenu = () => {
  console.log('Open favorite')
  emits('toggleFavoriteMenu')
}
</script>

<template>
  <nav class="flex justify-between mb-7 z-10 relative">
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
    <button @click="toggleFavoriteMenu" class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="rounded-full w-10 h-10 flex items-center justify-center leading-10 bg-white text-[#f53192] shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-transform hover:scale-110"
      >
        <img src="/bars-solid.svg" alt="bars icon" class="w-6 h-6" />
      </div>
    </button>
  </nav>
</template>
