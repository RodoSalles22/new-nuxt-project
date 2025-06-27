<template>
  <div class="flex justify-center items-center min-h-screen transition-colors">
    <div class="flex flex-wrap gap-8 max-w-5xl">
      <Card
        v-for="card in cards"
        :key="card.title"
        :icon="card.icon"
        :title="card.title"
        :description="card.description"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import Card from '~/components/card.vue'

const cards = [
  {
    icon: `badminton`,
    title: 'Badminton',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo volLorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluLorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluLorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluLorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluLorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluuptate et hic cum ratione a. Officia delectus illum perferendis maiores quia molestias vitae fugiat aspernatur alias corporis?'
  },
  {
    icon: `computer`,
    title: 'Developer',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluptate et hic cum ratione a. Officia delectus illum perferendis maiores quia molestias vitae fugiat aspernatur alias corporis?'
  },
  {
    icon: `person`,
    title: 'Personal Life',
    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde ab repudiandae, explicabo voluptate et hic cum ratione a. Officia delectus illum perferendis maiores quia molestias vitae fugiat aspernatur alias corporis?'
  }
]
</script>

<style scoped>
.perspective-1000 {
  perspective: 1000px;
}
</style>