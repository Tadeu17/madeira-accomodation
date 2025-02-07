<template>
  <header ref="headerRef" :style="styles" class="bg-white shadow-md z-50">
    <nav class="container mx-auto px-4 py-4 flex justify-between items-center">
      <h2 class="text-2xl font-bold text-indigo-600">{{ siteTitle }}</h2>
      <ul class="flex space-x-4">
        <li v-for="link in navLinks" :key="link.to">
          <NuxtLink :to="link.to" class="transition-colors duration-200" :class="[
            $route.path === link.to
              ? 'text-indigo-600'
              : 'text-gray-600 hover:text-indigo-600'
          ]">
            {{ link.text }}
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import { useFixedHeader } from 'vue-use-fixed-header'
import { useRoute } from 'vue-router'

const route = useRoute()
const headerRef = ref(null)
const { styles } = useFixedHeader(headerRef)

const siteTitle = 'Madeira Retreat'

const navLinks = [
  { to: '/', text: 'Home' },
  { to: '/about', text: 'About Madeira' },
  { to: '/links', text: 'Useful Links' }
]
</script>


<style scoped>
.Header {
  position: sticky;
  top: 0;
}
</style>
