<script setup>
import logo from "@/assets/images/logo.png";
</script>

<template>
  <div class="w-[full] h-40 bg-gray-800">
    <div
      class="w-[80%] mx-auto flex items-center justify-center text-center text-white py-8"
    >
      <div class="flex flex-col gap-4 items-center ">
        <div><img class="h-10 w-auto" :src="logo" alt="Vue Jobs" /></div>

        <p>Vue Jobs Inc @ 2024</p>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
