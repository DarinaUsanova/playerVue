<script setup>
import { ref } from 'vue'

import NavBar from './components/NavBar.vue'
import DisplayElement from './components/DisplayElement.vue'
import ControlButtons from './components/ControlButtons.vue'
import AppFooter from './components/AppFooter.vue'
import DropDownMenu from './components/DropDownMenu.vue'

const songs = ref([])
const currentSong = ref(null)
const isLoading = ref(true)
const isPlaying = ref(false)
const favoriteIsOpen = ref(false)

// const audioRef = ref(null)

const getSongData = async () => {
  try {
    const response = await fetch('http://localhost:5173/songs.json')
    const data = await response.json()
    songs.value = data
    currentSong.value = songs.value[0]
    isLoading.value = false
  } catch (error) {
    console.error('Ошибка загрузки данных:', error)
  }
}

const handlePlay = () => {
  isPlaying.value = !isPlaying.value
}

const toggleFavoriteMenu = () => {
  favoriteIsOpen.value = !favoriteIsOpen.value
}

getSongData()
</script>

<template>
  <div class="bg-[#9D8189] w-full h-screen flex items-center justify-center flex-wrap">
    <div class="bg-[#ffe0e5] w-2/5 px-6 py-9 text-center rounded-3xl relative">
      <NavBar @toggleFavoriteMenu="toggleFavoriteMenu" />
      <transition name="showHide">
        <DropDownMenu
          :currentSong="currentSong"
          :isLoading="isLoading"
          :songs="songs"
          v-show="favoriteIsOpen"
        />
      </transition>
      <DisplayElement :currentSong="currentSong" :isLoading="isLoading" :isPlaying="isPlaying" />
      <ControlButtons @play="handlePlay" :isPlaying="isPlaying" />
      <AppFooter />
    </div>
  </div>
</template>

<style scoped>
.showHide-enter-active {
  transition:
    transform 0.3s ease-out,
    opacity 0.3s ease-out;
}
.showHide-enter-from {
  transform: translateX(50%);
  opacity: 0;
}
.showHide-enter-to {
  transform: translateX(0);
  opacity: 1;
}

.showHide-leave-active {
  transition:
    transform 0.3s ease-in,
    opacity 0.3s ease-in;
}
.showHide-leave-from {
  transform: translateX(0);
  opacity: 1;
}
.showHide-leave-to {
  transform: translateX(-50%);
  opacity: 0;
}
</style>
