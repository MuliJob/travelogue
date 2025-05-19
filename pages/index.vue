<script setup lang="ts">
const authStore = useAuthStore();
</script>

<template>
  <div
    class="hero min-h-screen"
    style="background-image: url(https://worldlyadventurer.com/wp-content/uploads/2019/01/ethical-responsible-sustainable-tourism-1.jpg);"
  >
    <div class="hero-overlay" />
    <div class="hero-content text-neutral-content text-center">
      <div class="max-w-md">
        <h1 class="mb-5 text-5xl font-bold">
          Travelogue
        </h1>
        <p class="mb-5">
          Keep track of your travels and adventures with this simple travelogue app. Add locations, photos, and notes to create a digital journal of your journeys.
        </p>
        <AuthButton v-if="!authStore.user" />
        <NuxtLink v-else to="/dashboard" class="btn btn-primary">
          Start your journey
        </NuxtLink>
      </div>
    </div>
  </div>
</template>
