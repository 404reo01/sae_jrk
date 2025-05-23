<script setup>
import { ref, onMounted } from "vue";
import { useRoute } from "vue-router";
import axios from "axios";

const route = useRoute();
const vehicles = ref([]);
const filteredVehicles = ref([]);

// 🔹 Récupération des véhicules depuis l'API
onMounted(async () => {
  try {
    const response = await axios.get("http://localhost/api/vehicles");
    vehicles.value = response.data;
    filterVehicles(); // Appliquer le filtrage au chargement
  } catch (error) {
    console.error("Erreur lors du chargement des véhicules", error);
  }
});

// 🔹 Filtrage des véhicules selon localisation + dates
const filterVehicles = () => {
  filteredVehicles.value = vehicles.value.filter(vehicle => {
    return (!route.query.location || vehicle.localisation_vehicule === route.query.location) &&
           (!route.query.startDate || vehicle.date_début <= route.query.startDate) &&
           (!route.query.endDate || vehicle.date_fin >= route.query.endDate);
  });
};
</script>

<template>
  <div class="max-w-6xl mx-auto py-16">
    <h2 class="text-4xl font-bold text-gray-800 mb-6 text-center">Résultats de recherche</h2>

    <div v-if="filteredVehicles.length > 0" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-6">
      <div v-for="vehicle in filteredVehicles" :key="vehicle.id" class="bg-white shadow-lg rounded-lg p-4">
        <img :src="vehicle.image" alt="Voiture" class="w-full h-40 object-cover rounded-md">
        <h3 class="text-lg font-semibold mt-2">{{ vehicle.name }}</h3>
        <p class="text-gray-600">{{ vehicle.price }} €/jour</p>
      </div>
    </div>

    <p v-else class="text-gray-500 text-center mt-6">Aucun véhicule disponible pour cette période.</p>
  </div>
</template>