<template>
  <div class="min-h-screen flex flex-col">
    <TheHeader />
    <main class="flex-grow pt-16">
      <slot />
    </main>
    <TheFooter />
  </div>
</template>
