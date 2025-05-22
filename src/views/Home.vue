<script setup>
import Header from '@/components/header.vue'
import HeroSection from '@/components/HeroSection.vue'
import heroCar from '@/assets/hero_car.jpg'
import Service from '@/components/Services.vue'
import CarCard from '@/components/CardCar.vue'
import CardCategorie from '@/components/CardCategorie.vue'
const brands = [
  { name: 'audi', icon: new URL('@/assets/icon_audi.png', import.meta.url).href },
  { name: 'bmw', icon: new URL('@/assets/icon_bmw.png', import.meta.url).href },
  { name: 'chevrolet', icon: new URL('@/assets/icon_chevrolet.png', import.meta.url).href },
  { name: 'Volkswagen', icon: new URL('@/assets/icon_volkswagen.png', import.meta.url).href },
  { name: 'Toyota', icon: new URL('@/assets/icon_toyota.png', import.meta.url).href },
  { name: 'Ford', icon: new URL('@/assets/icon_ford.png', import.meta.url).href },
  { name: 'honda', icon: new URL('@/assets/icon_honda.png', import.meta.url).href },
  { name: 'Mercedes-Benz', icon: new URL('@/assets/icon_mercedes.png', import.meta.url).href },
  { name: 'Nissan', icon: new URL('@/assets/icon_nissan.png', import.meta.url).href },
  { name: 'Subaru', icon: new URL('@/assets/icon_subaru.png', import.meta.url).href },
  { name: 'Tesla', icon: new URL('@/assets/icon_tesla.png', import.meta.url).href },
  { name: 'polestar', icon: new URL('@/assets/icon_polestar.png', import.meta.url).href },
]

const categories = [
  { name: 'SUV', car: new URL('@/assets/icon_suv.png', import.meta.url).href },
  { name: 'Berline', car: new URL('@/assets/icon_berline.png', import.meta.url).href },
  { name: 'Coupé sport', car: new URL('@/assets/icon_coupesport.png', import.meta.url).href },
 
]

</script>

<template>
  <div
    class="min-h-screen bg-cover bg-center"
    :style="{ backgroundImage: `url(${heroCar})` }"
  >
    <Header />
    <HeroSection />
    
  </div>
  <div class="max-w-6xl mx-auto py-16">
    <h2 class="text-3xl font-bold text-gray-800 mb-6 text-center">Nos marques partenaires</h2>
    
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
      <CarCard
        v-for="brand in brands"
        :key="brand.name"
        :icon="brand.icon"
        :name="brand.name"
      />
    </div>
  </div>

  <div>
    <h2 class="text-3xl font-bold text-gray-800 mb-6 text-center">Nos catégories de voitures</h2>
    <div class="max-w-4xl mx-auto">
      <div class="grid grid-cols-3 gap-6 justify-items-center">
        <CardCategorie
          v-for="category in categories"
          :key="category.name"
          :car="category.car"
          :cate="category.name"
          class="bg-white shadow-lg rounded-lg p-4 flex flex-col items-center w-full"
        />
      </div>
    </div>
    <Service />
    </div>

  
</template>