<template>
  <div>
    <section class="py-16">
      <h1 class="text-4xl font-bold mb-8">Discover Madeira</h1>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
        <div>
          <h2 class="text-2xl font-semibold mb-4">Essential Tips</h2>
          <ul class="space-y-4">
            <li v-for="(tip, index) in tips" :key="index" class="flex items-start">
              <span class="text-indigo-600 mr-2">•</span>
              <p>{{ tip }}</p>
            </li>
          </ul>
        </div>
        <div class="space-y-6">
          <h2 class="text-2xl font-semibold">Must-Visit Places</h2>
          <div v-for="place in places" :key="place.name" class="bg-gray-50 p-6 rounded-lg">
            <h3 class="text-xl font-semibold mb-2">{{ place.name }}</h3>
            <p class="text-gray-600 mb-2">{{ place.description }}</p>
            <a :href="place.mapsLink" target="_blank" class="text-indigo-600 hover:text-indigo-800">View on Maps →</a>
          </div>
        </div>
      </div>

      <div class="bg-gray-50 p-8 rounded-lg">
        <h2 class="text-2xl font-semibold mb-6">Local Transportation</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div v-for="transport in transportation" :key="transport.type" class="p-4">
            <h3 class="font-semibold mb-2">{{ transport.type }}</h3>
            <p class="text-gray-600">{{ transport.info }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const tips = [
  "Best time to visit is between April and October for optimal weather",
  "Rent a car to explore the island's hidden gems",
  "Try the local Poncha drink and fresh seafood",
  "Pack comfortable walking shoes for levada walks",
  "Book popular restaurants in advance during peak season"
]

const places = [
  {
    name: "Funchal Old Town",
    description: "Historic center with painted doors, restaurants, and cable car access.",
    mapsLink: "https://maps.app.goo.gl/ewCxAfmRWNGXN8fj6"
  },
  {
    name: "Pico do Arieiro",
    description: "Third highest peak with stunning views above the clouds.",
    mapsLink: "https://maps.app.goo.gl/3VzJSYnqYn5B8Jss7"
  },
  {
    name: "Porto Moniz",
    description: "Natural swimming pools formed by volcanic lava.",
    mapsLink: "https://maps.app.goo.gl/VS1Buzuf2CWPFHyR6"
  },
  {
    name: "Botanical Garden",
    description: "Check out the beautiful Jardim botânico, a must see, and a good romantic go to place as well",
    mapsLink: "https://maps.app.goo.gl/fnhS2sypRzUrtNVm9"
  }
]

const transportation = [
  {
    type: "Bus Service",
    info: "Regular buses connect major towns. Get a rechargeable bus card for better rates. There are buses up to the accomodation, although owning your own transport is recommended"
  },
  {
    type: "Car Rental",
    info: "Multiple agencies available at the airport. Book in advance during peak season. Check useful links for possible recommendations."
  },
  {
    type: "Cable Cars",
    info: "Scenic transport options in Funchal, Monte, and other locations. Definitely a must try as well."
  }
]

useHead({
  title: 'About Madeira - Travel Tips and Guides',
  meta: [
    { name: 'description', content: 'Discover the best tips, places to visit, and local transportation options in Madeira.' }
  ]
})
</script>