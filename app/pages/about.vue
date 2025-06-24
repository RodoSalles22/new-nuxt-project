<template>
  <div class="flex flex-col items-center justify-center gap-4 h-screen">
    <h1 class="font-bold text-2xl text-warning">
      About Nuxt UI
    </h1>
    <p class="text-error">
      This is the about page for Nuxt UI.
    </p>
    <button class="btn btn-primary border border-inverted rounded-2xl p-2" @click="$router.push('/')">
      Go to Home Page
    </button>
  </div>
</template>
