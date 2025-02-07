<template>
  <div class="feature-card">
    <UCarousel v-slot="{ item }" :items="caroussel" arrows indicators :ui="{
      item: 'basis-full',
      wrapper: 'h-full',
      container: 'h-full w-full',
    }">
      <img :src="item.src" :alt="item.alt" width="300" height="300" class="w-full h-full object-cover" />
    </UCarousel>
    <h3 class="text-xl font-semibold mb-2">{{ title }}</h3>
    <p class="text-gray-600">{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  caroussel: {
    type: Array,
    required: true
  }
})
</script>
