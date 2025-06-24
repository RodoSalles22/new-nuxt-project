<template>
  <nav>
    <ul>
      <li
      v-for="(item, idx) in items"
      :key="item.label"
      >
      <NuxtLink
      :to="item.href"
          class="fancy-link"
          :data-text="item.label"
          :style="{ '--clr': colors[idx % colors.length] }"
          >
          {{ item.label }}
        </NuxtLink>
      </li>
    </ul>
    <button
    class="mode-btn"
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
  { label: 'About', href: '/about' },
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
* {
  box-sizing: border-box;
  padding: 10px;
  margin: 10px;
  font-family: 'Mochiy Pop One', sans-serif;
}

nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 10vh;
  width: 100vw;
  justify-content: center;
  position: fixed;
  top: 0;
}

ul {
  position: relative;
  display: flex;
  flex-direction: row; /* <-- horizontal */
  gap: 5px;           /* mais espaçamento entre itens */
  margin-bottom: 5px;
}
ul li {
  position: relative;
  list-style: none;
}
.fancy-link {
  font-size: 4em;
  text-decoration: none;
  letter-spacing: 2px;
  line-height: 1em;
  text-transform: uppercase;
  color: transparent;
  -webkit-text-stroke: 1px rgba(153, 152, 152, 0.5);
  position: relative;
  display: inline-block;
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
.mode-btn {
  background: none;
  border: none;
  font-size: 2em;
  cursor: pointer;
  color: #fff;
  margin-top: 1rem;
  transition: color 0.3s ease;
  position: fixed;
  top: 10px;
  right: 10px;
}
</style>