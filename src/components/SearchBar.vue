<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();

// 🔹 Variables qui stockent les valeurs du formulaire
const filters = ref({
  location: "",
  startDate: "",
  endDate: ""
});

// 🔍 Fonction qui envoie les données à la page de recherche
const searchVehicles = () => {
  router.push({
    path: "/search-results",
    query: {
      location: filters.value.location,
      startDate: filters.value.startDate,
      endDate: filters.value.endDate
    }
  });
};
</script>

<template>
  <div class="bg-white shadow-md rounded-lg p-6 flex flex-col md:flex-row gap-4 items-center justify-between">
    
    <input v-model="filters.location" type="text" placeholder="Entrez une localisation" 
      class="border p-2 rounded-md w-full md:w-auto">

    <input v-model="filters.startDate" type="date"
      class="border p-2 rounded-md w-full md:w-auto">

    <input v-model="filters.endDate" type="date"
      class="border p-2 rounded-md w-full md:w-auto">


    <button @click="searchVehicles"
      class="bg-black text-white px-6 py-2 rounded mt-2 md:mt-0 md:ml-6">
      Trouver véhicule
    </button>
  </div>
</template>