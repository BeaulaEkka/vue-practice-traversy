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
        src="https://img.freepik.com/free-photo/blonde-female-executive-posing-with-smile-arms-crossed-brainstorm-with-managers-indoor-portrait-european-student-spending-time-hall-with-asian-african-friends_197531-3755.jpg?t=st=1722795336~exp=1722798936~hmac=29dbbd9f201d6a7c6c342e1e605f59db228afe44c660c17b74eaa6e98dced551&w=2000"
        alt="office"
        class="w-full h-[60vh] object-cover"
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
