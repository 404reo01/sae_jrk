<template>
  <header class="w-full bg-black flex items-center justify-between px-8 py-4">
    <div class="flex-1 flex justify-start">
      <img src="@/assets/logo.png" alt="Logo" class="h-24" />
    </div>
    <div class="flex-1 flex justify-end space-x-4">
      <router-link
        to="/profile"
        class="border border-white text-white rounded-lg px-6 py-2 hover:bg-white hover:text-black transition"
      >
        Voir profil
      </router-link>
      <router-link
        to="/login"
        class="border border-white text-white rounded-lg px-6 py-2 hover:bg-white hover:text-black transition"
      >
        Login / Register
      </router-link>
    </div>
  </header>
</template>

