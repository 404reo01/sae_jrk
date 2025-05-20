<script setup>
import Header from '@/components/header.vue'
import HeroSection from '@/components/HeroSection.vue'
import heroCar from '@/assets/hero_car.jpg'
</script>

<template>
  <div
    class="min-h-screen bg-cover bg-center"
    :style="{ backgroundImage: `url(${heroCar})` }"
  >
    <Header />
    <HeroSection />
  </div>
</template>