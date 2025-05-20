<template>
  <div class="flex justify-between pt-5 ">
    <img src="@/assets/logo.png" alt="" class="size-20 flex items-center justify-start ml-5" />
  
    <div class="border-white border-2 text-white rounded-2xl flex justify-end w-fit px-2.5 h-15">
      <div class="flex items-center space-x-20 text-xl justify-center">    
        <router-link to="/login" class="hover:underline flex justify-end">Login / Register</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>