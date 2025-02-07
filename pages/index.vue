<template>
  <div>
    <section class="container mx-auto px-4 py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
        <div class="space-y-6">
          <h1 class="text-4xl font-bold">Experience Madeira in Style</h1>
          <p class="text-xl text-gray-600">
            Discover our beautiful Airbnb property nestled in the heart of Madeira. Perfect for your island getaway.
          </p>
          <a href="#booking"
            class="inline-block bg-indigo-600 text-white px-6 py-3 rounded-lg hover:bg-indigo-700 transition-colors">
            Book Now
          </a>
        </div>

        <div class="h-[400px] max-w-[600px] relative  mx-auto rounded-lg overflow-hidden shadow-lg">
          <UCarousel v-slot="{ item }" ref="carouselRef" :items="carouselItems" arrows indicators :ui="{
            wrapper: 'h-full',
            container: 'h-full w-full',
          }">
            <img :src="item.src" :alt="item.alt" class="w-full h-full object-cover" />
          </UCarousel>
        </div>
      </div>
    </section>

    <section class="features py-16">
      <h2 class="text-3xl font-semibold mb-8 text-center">Property Rooms</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <FeatureCard v-for="feature in features" :key="feature.title" :title="feature.title"
          :description="feature.description" :image="feature.image" />
      </div>
    </section>

    <section class="amenities py-16 bg-gray-50">
      <h3 class="text-3xl font-semibold mb-8 text-center">Amenities & Features</h3>
      <div class="container mx-auto grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="amenity in amenities" :key="amenity.title" class="flex items-start space-x-4">
          <div class="w-12 h-12 flex items-center justify-center rounded-full bg-indigo-100">
            <Icon :name="amenity.icon" class="h-6 w-6 text-indigo-600" />
          </div>
          <div>
            <h4 class="text-lg font-semibold mb-2">{{ amenity.title }}</h4>
            <p class="text-gray-600">{{ amenity.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <section id="booking" class="booking py-16 bg-gray-100">
      <h2 class="text-3xl font-semibold mb-8 text-center">Book Your Stay</h2>
      <UForm class="max-w-lg mx-auto" :state="state" @submit="onSubmit">
        <div class="grid grid-cols-2 gap-4 mb-4">
          <div>
            <UFormGroup label="Check-in">
              <UInput v-model="state.checkIn" type="date" required />
            </UFormGroup>
          </div>
          <div>
            <UFormGroup label="Check-out">
              <UInput v-model="state.checkOut" type="date" required  />
            </UFormGroup>
          </div>
        </div>
        <div class="mb-4">
          <UFormGroup label="Number of Guests">
            <UInput v-model="state.guests" type="number" :min="1" :max="6" required />
          </UFormGroup>
        </div>
        <UButton type="submit" color="primary" variant="solid" block>
          Check Availability
        </UButton>
      </UForm>
    </section>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: 'Madeira Retreat - Your Perfect Island Getaway',
  meta: [
    { name: 'description', content: 'Experience the beauty of Madeira in our stunning Airbnb property. Book your stay today and enjoy breathtaking views, modern amenities, and a prime location.' },
    { name: 'keywords', content: 'Madeira, Airbnb, accomodation, vacation rental, island getaway, Portugal' },
  ],
})

const carouselItems = [
  {
    src: '/feature-1.jpg',
    alt: 'Beautiful view of the property'
  },
  {
    src: '/feature-1.jpg',
    alt: 'Interior of the property'
  },
  {
    src: '/feature-1.jpg',
    alt: 'Property amenities'
  }
]
const carouselRef = ref()
const carouselAutoplayTimer = 3000
onMounted(() => {
  setInterval(() => {
    if (!carouselRef.value) return

    if (carouselRef.value.page === carouselRef.value.pages) {
      return carouselRef.value.select(0)
    }

    carouselRef.value.next()
  }, carouselAutoplayTimer)
})

const features = [
  {
    title: "Room 1",
    description: "Suite, a Queen size bed with private WC with stunning overview landscape of funchal",
    image: "/feature-1.jpg"
  },
  {
    title: "Room 2",
    description: "Very spacious room with Quee size bed, plenty of natural light and a desk for you use.",
    image: "/feature-1.jpg"
  },
  {
    title: "Room 3",
    description: "Cosy room with the essentials for a very nice stay, Queen size bed to make sure you have the best sleep.",
    image: "/feature-1.jpg"
  }
];

const amenities = [
  {
    icon: 'mdi:wifi',
    title: 'High-Speed WiFi',
    description: 'Fast and reliable internet connection for work or entertainment'
  },
  {
    icon: 'mdi:television',
    title: 'Large TV',
    description: 'Smart TV with streaming capabilities'
  },
  {
    icon: 'mdi:guitar-acoustic',
    title: 'Guitar Available',
    description: 'Acoustic guitar for music lovers'
  },
  {
    icon: 'mdi:home-roof',
    title: 'Rooftop Access',
    description: 'Private rooftop area with panoramic views'
  },
  {
    icon: 'mdi:sofa',
    title: 'Private Lounge',
    description: 'Comfortable lounge area with stunning views'
  },
  {
    icon: 'mdi:grill',
    title: 'BBQ Grill',
    description: 'Outdoor grill for al fresco dining'
  },
  {
    icon: 'mdi:garage',
    title: 'Private Garage',
    description: 'Secure parking space for your vehicle'
  },
  {
    icon: 'mdi:bed-double',
    title: '3 Bedrooms',
    description: 'Comfortable sleeping arrangements with quality bedding'
  },
  {
    icon: 'mdi:kitchen',
    title: '100% Kitchen',
    description: 'Fully equipped with appliances and cooking essentials'
  },
  {
    icon: 'mdi:balcony',
    title: 'Spacious Balcony',
    description: 'Large terrace with stunning mountain and ocean views'
  },
  {
    icon: 'mdi:mountain',
    title: 'Scenic Views',
    description: 'Panoramic views of Madeira\'s mountains and coastline'
  },
  {
    icon: 'mdi:desk',
    title: 'Work Setup',
    description: 'Dedicated workspace with desk and comfortable seating'
  },
  {
    icon: 'mdi:washing-machine',
    title: 'Laundry',
    description: 'In-unit washing machine for your convenience'
  },
  {
    icon: 'mdi:shower',
    title: '3 Bathrooms',
    description: 'Clean bathrooms with showers'
  }
]

const state = reactive({
  checkIn: undefined,
  checkOut: undefined,
  guests: undefined
})

import type { FormSubmitEvent } from '#ui/types'
const onSubmit = (event: FormSubmitEvent<typeof state>) => {
  console.log(event.data)
}
</script>
