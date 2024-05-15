<script setup>
import { defineEmits } from 'vue'

const emits = defineEmits(['play'])

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
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 512 512"
          class="w-[16px] h-[17px] fill-[#f53192]"
        >
          <path
            d="M459.5 440.6c9.5 7.9 22.8 9.7 34.1 4.4s18.4-16.6 18.4-29V96c0-12.4-7.2-23.7-18.4-29s-24.5-3.6-34.1 4.4L288 214.3V256v41.7L459.5 440.6zM256 352V256 128 96c0-12.4-7.2-23.7-18.4-29s-24.5-3.6-34.1 4.4l-192 160C4.2 237.5 0 246.5 0 256s4.2 18.5 11.5 24.6l192 160c9.5 7.9 22.8 9.7 34.1 4.4s18.4-16.6 18.4-29V352z"
          />
        </svg>
      </div>
    </button>
    <button @click="handlePlay" class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="w-[60px] h-[60px] m-5 bg-[#f53192] inline-flex scale-150 items-center justify-center rounded-full text-white cursor-pointer shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-shadow hover:shadow-[0_5px_10px_rgba(255,26,26,0.436)]"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 384 512"
          class="w-[16px] h-[17px] fill-white"
        >
          <path
            d="M73 39c-14.8-9.1-33.4-9.4-48.5-.9S0 62.6 0 80V432c0 17.4 9.4 33.4 24.5 41.9s33.7 8.1 48.5-.9L361 297c14.3-8.7 23-24.2 23-41s-8.7-32.2-23-41L73 39z"
          />
        </svg>
      </div>
    </button>
    <button class="bg-transparent border-0 cursor-pointer outline-none">
      <div
        class="w-[60px] h-[60px] m-5 bg-white inline-flex items-center justify-center rounded-full text-[#f53192] cursor-pointer shadow-[0_5px_10px_rgba(255,26,26,0.22)] duration-400 transition-shadow hover:shadow-[0_5px_10px_rgba(255,26,26,0.436)]"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 512 512"
          class="w-[16px] h-[17px] fill-[#f53192]"
        >
          <path
            d="M52.5 440.6c-9.5 7.9-22.8 9.7-34.1 4.4S0 428.4 0 416V96C0 83.6 7.2 72.3 18.4 67s24.5-3.6 34.1 4.4L224 214.3V256v41.7L52.5 440.6zM256 352V256 128 96c0-12.4 7.2-23.7 18.4-29s24.5-3.6 34.1 4.4l192 160c7.3 6.1 11.5 15.1 11.5 24.6s-4.2 18.5-11.5 24.6l-192 160c-9.5 7.9-22.8 9.7-34.1 4.4s-18.4-16.6-18.4-29V352z"
          />
        </svg>
      </div>
    </button>
  </div>
</template>
