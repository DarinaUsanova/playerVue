<script setup>
import { defineProps } from 'vue'

const emits = defineEmits(['play'])
const { isPlaying } = defineProps(['isPlaying'])

const handlePlay = () => {
  emits('play')
}
</script>

<template>
  <div class="flex justify-center items-center">
    <button class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="w-[60px] h-[60px] m-5 bg-white inline-flex items-center justify-center rounded-full text-[#f53192] cursor-pointer shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-shadow hover:shadow-[0_5px_10px_rgba(255,26,26,0.436)]"
      >
        <img src="/backward-solid.svg" alt="" class="w-[16px] h-[17px]" />
      </div>
    </button>
    <button @click="handlePlay" class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="w-[60px] h-[60px] m-5 bg-[#f53192] inline-flex scale-150 items-center justify-center rounded-full text-white cursor-pointer shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-shadow hover:shadow-[0_5px_10px_rgba(255,26,26,0.436)]"
      >
        <img
          :src="isPlaying ? '/pause-solid.svg' : '/play-solid.svg'"
          alt="play/pause button image"
          class="w-[16px] h-[17px]"
        />
      </div>
    </button>
    <button class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="w-[60px] h-[60px] m-5 bg-white inline-flex items-center justify-center rounded-full text-[#f53192] cursor-pointer shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-shadow hover:shadow-[0_5px_10px_rgba(255,26,26,0.436)]"
      >
        <img src="/backward-solid.svg" alt="" class="w-[16px] h-[17px] rotate-180" />
      </div>
    </button>
  </div>
</template>
