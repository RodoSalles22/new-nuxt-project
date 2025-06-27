<template>
  <div class="group perspective-1000 w-[300px] h-[200px] relative">
    <div class="absolute inset-0 transition-transform duration-500 [transform-style:preserve-3d] group-hover:[transform:rotateY(180deg)]">
      <!-- Front -->
      <div class="absolute inset-0 dark:bg-gray-800 bg-amber-300 flex flex-col justify-center items-center rounded-lg shadow-lg [backface-visibility:hidden] transition-all duration-500 group-hover:shadow-[0_0_60px_white,20px_0_80px_fuchsia,-20px_0_80px_cyan,20px_0_300px_fuchsia,-20px_0_300px_cyan,0_0_50px_white,-10px_0_80px_fuchsia,10px_0_80px_cyan]">
        <div class="opacity-20 group-hover:opacity-100 transition-opacity duration-500 text-center">
          <span v-html="icons[icon]" />
          <h3 class="text-white text-lg mt-2">{{ title }}</h3>
        </div>
      </div>
      <!-- Back -->
      <div class="absolute inset-0 bg-gray-100 flex flex-col justify-center items-center rounded-lg shadow-2xl p-5 [backface-visibility:hidden] [transform:rotateY(180deg)] transition-all duration-500">
        <p class="text-gray-800 text-sm mb-4">{{ description }}</p>
        <a
          href="#"
          class="inline-block px-4 py-2 border border-dashed border-gray-700 text-gray-900 rounded transition-all duration-300 hover:bg-gray-800 hover:text-white hover:shadow-inner hover:border-solid"
        >
          Read More
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
  icon: string
  title: string
  description: string
}>()

const icons: Record<string, string> = {
  badminton: `<img src="https://cdn-icons-png.flaticon.com/512/8540/8540840.png" fill="white" viewBox="0 0 24 24" class="w-12 h-12 mx-auto">`,
  computer: `<img src="https://cdn-icons-png.flaticon.com/512/4854/4854186.png" fill="white" viewBox="0 0 24 24" class="w-12 h-12 mx-auto">`,
  person: `<svg xmlns="http://www.w3.org/2000/svg" fill="white" viewBox="0 0 24 24" class="w-12 h-12 mx-auto"><path d="M16.365 1.43c0 1.14-.93 2.07-2.07 2.07-.04 0-.08 0-.12-.01.01-.13.02-.26.02-.39 0-1.14.93-2.07 2.07-2.07.04 0 .08 0 .12.01-.01.13-.02.26-.02.39zm2.13 4.13c-1.13-.13-2.34.66-2.95.66-.62 0-1.56-.64-2.57-.62-1.32.02-2.53.77-3.2 1.96-1.37 2.38-.35 5.89.98 7.82.65.95 1.42 2.01 2.43 1.97.97-.04 1.34-.63 2.51-.63 1.17 0 1.5.63 2.52.61 1.04-.02 1.69-.97 2.34-1.92.74-1.08 1.05-2.13 1.06-2.18-.02-.01-2.04-.78-2.06-3.09-.02-1.93 1.57-2.85 1.65-2.9-.91-1.33-2.32-1.48-2.82-1.5zm-2.02 13.13c-.48 0-.96-.14-1.36-.39-.4-.25-.74-.61-.98-1.04-.24-.43-.36-.92-.36-1.41 0-.49.12-.98.36-1.41.24-.43.58-.79.98-1.04.4-.25.88-.39 1.36-.39.48 0 .96.14 1.36.39.4.25.74.61.98 1.04.24.43.36.92.36 1.41 0 .49-.12.98-.36 1.41-.24.43-.58.79-.98 1.04-.4.25-.88.39-1.36.39z"/></svg>`
}
</script>

<style scoped>
.perspective-1000 {
  perspective: 1000px;
}
</style>