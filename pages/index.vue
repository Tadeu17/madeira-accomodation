<template>
  <div>
    <section class="hero py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
        <div>
          <h1 class="text-4xl font-bold mb-4">Experience Madeira in Style</h1>
          <p class="text-xl text-gray-600 mb-6">Discover our beautiful Airbnb property nestled in the heart of Madeira.
            Perfect for your island getaway.</p>
          <a href="#booking"
            class="bg-indigo-600 text-white px-6 py-3 rounded-lg hover:bg-indigo-700 transition duration-300">
            Book Now
          </a>
        </div>
        <div>
          <img src="/feature-1.jpg" alt="Madeira Retreat Property" class="rounded-lg shadow-lg" />
        </div>
      </div>
    </section>

    <section class="features py-16">
      <h2 class="text-3xl font-semibold mb-8 text-center">Property Highlights</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <FeatureCard v-for="feature in features" :key="feature.title" :title="feature.title"
          :description="feature.description" :image="feature.image" />
      </div>
    </section>

    <section id="booking" class="booking py-16 bg-gray-100">
      <h2 class="text-3xl font-semibold mb-8 text-center">Book Your Stay</h2>
      <form class="max-w-lg mx-auto">
        <div class="grid grid-cols-2 gap-4 mb-4">
          <div>
            <label for="check-in" class="block mb-2">Check-in</label>
            <input type="date" id="check-in" class="w-full px-4 py-2 rounded-lg border border-gray-300" required />
          </div>
          <div>
            <label for="check-out" class="block mb-2">Check-out</label>
            <input type="date" id="check-out" class="w-full px-4 py-2 rounded-lg border border-gray-300" required />
          </div>
        </div>
        <div class="mb-4">
          <label for="guests" class="block mb-2">Number of Guests</label>
          <input type="number" id="guests" min="1" max="6" class="w-full px-4 py-2 rounded-lg border border-gray-300"
            required />
        </div>
        <button type="submit"
          class="w-full bg-indigo-600 text-white px-6 py-3 rounded-lg hover:bg-indigo-700 transition duration-300">Check
          Availability</button>
      </form>
    </section>
  </div>
</template>

<script setup lang="ts">
const features = [
  {
    title: "Stunning Views",
    description: "Wake up to breathtaking ocean and mountain vistas every day.",
    image: "/feature-1.jpg"
  },
  {
    title: "Modern Amenities",
    description: "Enjoy a fully equipped kitchen, high-speed Wi-Fi, and more.",
    image: "/feature-1.jpg"
  },
  {
    title: "Prime Location",
    description: "Easy access to Madeira's best attractions and hidden gems.",
    image: "/feature-1.jpg"
  }
];

useHead({
  title: 'Madeira Retreat - Your Perfect Island Getaway',
  meta: [
    { name: 'description', content: 'Experience the beauty of Madeira in our stunning Airbnb property. Book your stay today and enjoy breathtaking views, modern amenities, and a prime location.' },
    { name: 'keywords', content: 'Madeira, Airbnb, accomodation, vacation rental, island getaway, Portugal' },
  ],
})
</script>
