<script setup lang="ts">
import AppNavBar from '~/layout/AppNavBar.vue'
</script>

<template>
  <NuxtLayout>
    <AppNavBar />
    <slot />
    <NuxtPage />
  </NuxtLayout>
</template>