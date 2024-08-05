<script setup>
import { computed } from "vue";
import "primeicons/primeicons.css";

const props = defineProps({
  job: Object,
});

const showAllDescription = ref(false);
const toggleFullDescription = () => {
  showAllDescription.value = !showAllDescription.value;
};

const truncatedDescription = computed(() => {
  let description = props.job.description;
  if (!showAllDescription.value) {
    description = description.substring(0, 100) + " ...";
  }
  return description;
});
</script>

<template>
  <div>
    <!-- Job Listing 1 -->
    <div class="bg-white rounded-xl shadow-md relative">
      <div class="p-4">
        <div class="mb-6">
          <div class="text-gray-600 my-2">{{ job.type }}</div>
          <h3 class="text-xl font-bold">{{ job.title }}</h3>
        </div>

        <div class="mb-5">
          {{ truncatedDescription }}

          <div
            @click="toggleFullDescription"
            class="hover:text-blue-500 text-blue-400 py-4"
          >
            {{ showAllDescription ? "Read Less" : "Read More" }}
          </div>
        </div>

        <h3 class="text-green-500 mb-2">{{ job.salary }}</h3>

        <div class="border border-gray-100 mb-5"></div>

        <div class="flex flex-col lg:flex-row justify-between mb-4">
          <div class="text-gray-400 mb-3">
            <i class="fa-solid fa-location-dot text-lg"></i>
            <i class="pi pi-map-marker" style="font-size: 1rem"></i>
            {{ job.location }}
          </div>
          <a
            :href="'/job/' + job.id"
            class="h-[36px] bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg text-center text-sm"
          >
            Read More
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
