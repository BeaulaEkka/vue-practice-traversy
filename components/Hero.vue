<script setup>
import { defineProps } from "vue";
defineProps({
  title: { type: String, default: "How to become a Dev" },
  subTitle: { type: String, default: "This is blank!" },
});
</script>

<template>
  <!-- Hero -->
  <section class="bg-indigo-400 mb-4 relative">
    <div class="w-full h-90 border border-red-500">
      <img
        src="https://img.freepik.com/free-photo/caucasian-young-woman-s-half-length-portrait-yellow-studio_155003-22408.jpg?t=st=1722795629~exp=1722799229~hmac=f9c163d0424269f730248f5dede7f5b6e10c26cb0b7fa9405e8a2e63011004f7&w=2000"
        alt="office"
        class="w-full h-[65vh] object-cover"
      />
    </div>
    <div
      class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center absolute top-40 right-0 left-0"
    >
      <div class="text-center">
        <h1 class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl">
          {{ title }}
        </h1>
        <p class="my-4 text-xl text-white">
          {{ subTitle }}
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
