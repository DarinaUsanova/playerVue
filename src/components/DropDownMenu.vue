<script setup>
import { defineProps } from 'vue'

defineProps({
  currentSong: {
    Type: Object
  },
  isLoading: {
    Type: Boolean
  },
  songs: {
    Type: Array
  }
})

const emit = defineEmits(['setCurrentSong'])

const handlClick = (song) => {
  emit('setCurrentSong', song)
}
</script>

<template>
  <div
    class="flex justify-center bg-[#f53192] bg-opacity-45 absolute top-0 right-0 rounded-t-3xl w-full p-5"
  >
    <ul class="text-white flex flex-col mt-16 w-4/5">
      <li
        @click="handlClick(song)"
        v-for="song in songs"
        :key="song.id"
        :class="{ 'text-[#f53192]': song.id === currentSong.id }"
        class="cursor-pointer"
      >
        {{ song.title }} - {{ song.name }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
