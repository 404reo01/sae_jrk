<template>
  <div class="bg-white shadow-lg rounded-lg p-4 flex flex-col items-center">
    <img :src="car" alt="Logo marque" class="w-16 h-16 object-contain">
    <h3 class="text-lg font-semibold text-gray-700 mt-2">{{ cate }}</h3>
  </div>
</template>

<script setup>
defineProps({
  car: String,
  cate: String,
});
</script>
