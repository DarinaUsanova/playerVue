<script setup>
import { ref, watch } from 'vue'

const props = defineProps(['currentSong', 'isLoading', 'isPlaying'])

const audioRef = ref(null)

watch(
  () => props.currentSong,
  () => {
    if (props.isPlaying.value) {
      audioRef.value.play()
    }
  }
)

watch(
  () => props.isPlaying,
  (newValue) => {
    if (newValue) {
      audioRef.value.play()
    } else {
      audioRef.value.pause()
    }
  }
)
</script>

<template>
  <div class="flex flex-col items-center" v-if="!props.isLoading">
    <img
      :key="props.currentSong.id"
      :src="props.currentSong.cover"
      alt="Gorillaz album cover"
      class="w-[220px] rounded-full border-8 border-solid border-white"
    />
    <h1 class="text-xl font-normal text-gray-900 mt-5">{{ props.currentSong.name }}</h1>
    <p class="text-sm text-gray-900">{{ props.currentSong.title }}</p>
    <audio
      ref="audioRef"
      :key="props.currentSong.id"
      :src="props.currentSong.source"
      preload="auto"
    >
      <source :src="props.currentSong.source" type="audio/mpeg" />
    </audio>
    <input
      type="range"
      value="0"
      id="progress"
      class="appearance-none w-full h-[6px] bg-[#f53192] rounded-md cursor-pointer mt-[40px] mb-[30px]"
    />
    <input
      type="range"
      min="0"
      max="1"
      step="0.1"
      value="1"
      id="volume"
      class="appearance-none h-1 bg-[#f53192] rounded cursor-pointer mb-1"
    />
  </div>
</template>

<style scoped>
#progress::-webkit-slider-thumb {
  -webkit-appearance: none;
  background: #f53192;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 8px solid #fff;
  box-shadow: 0 5px 5px rgba(255, 26, 26, 0.22);
  transition: box-shadow 0.3s;
}
#progress::-webkit-slider-thumb:hover {
  box-shadow: 0 10px 20px rgba(255, 26, 26, 0.436);
}
#volume {
  -webkit-appearance: none;
  height: 4px;
  background: #f53192;
  border-radius: 4px;
  cursor: pointer;
  margin-bottom: 40px;
}
#volume::-webkit-slider-thumb {
  -webkit-appearance: none;
  background: #f53192;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 4px solid #fff;
  box-shadow: 0 5px 5px rgba(255, 26, 26, 0.22);
  transition: box-shadow 0.3s;
}
#volume::-webkit-slider-thumb:hover {
  box-shadow: 0 10px 20px rgba(255, 26, 26, 0.436);
}
</style>
