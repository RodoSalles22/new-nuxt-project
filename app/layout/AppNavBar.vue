<template>
  <nav class="fixed top-0 left-0 z-50 w-full min-h-[10vh] flex items-center justify-center ">
    <ul class="flex flex-row gap-10 m-0 p-0 list-none">
      <li
        v-for="(item, idx) in items"
        :key="item.label"
        class="relative"
      >
        <NuxtLink
          :to="item.href"
          class="fancy-link font-mochiy text-[2.5em] uppercase tracking-wider leading-none inline-block relative transition-colors duration-300"
          :data-text="item.label"
          :style="{ '--clr': colors[idx % colors.length] }"
        >
          {{ item.label }}
        </NuxtLink>
      </li>
    </ul>
    <button
      class="ml-8 text-white text-2xl bg-transparent border-none cursor-pointer transition-colors duration-300 relative"
      aria-label="Alternar modo escuro/claro"
      @click="mode.value = mode.value === 'dark' ? 'light' : 'dark'"
    >
      <span v-if="mode.value === 'dark'">🌙</span>
      <span v-else>☀️</span>
    </button>
  </nav>
</template>

<script setup lang="ts">
const items = [
  { label: 'Home', href: '/' },
  { label: 'About Me', href: '/about' },
  { label: 'Contact', href: '/contact' }
]

const colors = [
  '#00FFB2',
  '#FF00C8',
  '#FFD600',
  '#00C8FF',
  '#FF6B00'
]

const mode = useColorMode()
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Mochiy+Pop+One&display=swap');
.font-mochiy {
  font-family: 'Mochiy Pop One', sans-serif;
}
.fancy-link {
  color: transparent;
  -webkit-text-stroke: 1px rgba(31, 31, 31, 0.5);
}
.dark .fancy-link {
  color: transparent;
  -webkit-text-stroke: 1px rgba(181, 181, 181, 0.5);
}
.fancy-link::before {
  content: attr(data-text);
  position: absolute;
  color: var(--clr);
  width: 0;
  overflow: hidden;
  transition: 1s;
  border-right: 8px solid var(--clr);
  -webkit-text-stroke: 1px var(--clr);
  left: 0;
  top: 0;
  height: 100%;
  white-space: nowrap;
}
.fancy-link:hover::before {
  width: 100%;
  filter: drop-shadow(0 0 25px var(--clr));
}
</style>