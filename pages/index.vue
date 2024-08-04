<script setup></script>

<template>
  <div class="">
    <div>
      <Hero title="How to become a developer" subTitle="This is a Subtitle" />

      <!-- Developers and Employers -->
      <HomeCards />

      <!-- Browse Jobs -->
      <JobListings :limit="3" :showButton="true" />
    </div>
  </div>
</template>

<style scoped></style>
