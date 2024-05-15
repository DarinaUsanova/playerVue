<script setup>
import { ref } from 'vue'

import NavBar from './components/NavBar.vue'
import DisplayElement from './components/DisplayElement.vue'
import ControlButtons from './components/ControlButtons.vue'
import AppFooter from './components/AppFooter.vue'

const songs = ref([])
const currentSong = ref(null)
const isLoading = ref(true)

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
  console.log('Playing song')
}

getSongData()
</script>

<template>
  <div class="bg-[#9D8189] w-full h-screen flex items-center justify-center flex-wrap">
    <div class="bg-[#ffe0e5] w-2/5 px-6 py-9 text-center rounded-3xl">
      <NavBar />
      <DisplayElement :currentSong="currentSong" :isLoading="isLoading" />
      <ControlButtons @play="handlePlay" />
      <AppFooter />
    </div>
  </div>
</template>
