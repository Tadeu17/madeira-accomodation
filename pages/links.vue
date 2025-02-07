<template>
  <div>
    <section class="py-16">
      <h1 class="text-4xl font-bold mb-8">Useful Links</h1>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="category in categories" :key="category.title" class="bg-gray-50 p-6 rounded-lg">
          <h2 class="text-2xl font-semibold mb-4">{{ category.title }}</h2>
          <div class="space-y-4">
            <div v-for="link in category.links" :key="link.name"
              class="p-4 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow">
              <h3 class="font-semibold mb-2">{{ link.name }}</h3>
              <p class="text-gray-600 text-sm mb-3">{{ link.description }}</p>
              <a :href="link.url" target="_blank"
                class="inline-flex items-center text-indigo-600 hover:text-indigo-800">
                Get Started →
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
const categories = [
  {
    title: "Digital Nomad Essentials",
    links: [
      {
        name: "Croissant",
        description: "Access coworking spaces worldwide with a single membership.",
        url: "https://www.getcroissant.com/a/jose96"
      },
      {
        name: "Revolut",
        description: "Smart digital banking with great exchange rates. Works worldwide.",
        url: "https://revolut.com/referral/?referral-code=jostadglmi!FEB1-25-AR-ON-L1-REVPRO"
      },
      {
        name: "Wise",
        description: "Transfer money internationally at real exchange rates. Works worldwide.",
        url: "https://wise.com/invite/ahpc/josep5415"
      }
    ]
  },
  {
    title: "Local Services",
    links: [
      {
        name: "Car Rentals",
        description: "Discover cars tends to bring very good deals for car rentals!",
        url: 'https://tobedefined.com'
      },
      {
        name: "Bolt",
        description: "Reliable Madeira online Taxi service.",
        url: "https://bolt.eu/referral/your-ref-code"
      },
      {
        name: "Glovo",
        description: "Food and grocery delivery service.",
        url: "https://glovoapp.com/referral/your-ref-code"
      }
    ]
  },
  {
    title: "Travel Insurance",
    links: [
      {
        name: "SafetyWing",
        description: "Travel medical insurance for nomads.",
        url: "https://safetywing.com/nomad-insurance/profile?referralToken=a1d04b89-30fe-46e5-b99d-423541adea22"
      },
      {
        name: "World Nomads",
        description: "Comprehensive travel insurance coverage.",
        url: "https://worldnomads.com/referral/your-ref-code"
      }
    ]
  }
]

useHead({
  title: 'Useful Links - Services and Resources for Your Stay',
  meta: [
    { name: 'description', content: 'Find essential services and resources for your stay in Madeira, from coworking spaces to local services.' }
  ]
})
</script>
