<script setup>
import NavBar from './components/NavBar.vue'
import DisplayElement from './components/DisplayElement.vue'
</script>

<template>
  <div class="bg-[#9D8189] w-full h-screen flex items-center justify-center flex-wrap">
    <div class="bg-[#ffe0e5] w-2/5 px-6 py-9 text-center rounded-3xl">
      <NavBar />
      <DisplayElement />
    </div>
  </div>
</template>

<style scoped></style>
