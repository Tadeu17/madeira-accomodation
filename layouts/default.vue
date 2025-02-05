<template>
  <div class="min-h-screen flex flex-col">
    <TheHeader />
    <main class="container mx-auto px-4 pt-16 flex-grow">
      <slot />
    </main>
    <TheFooter />
  </div>
</template>
