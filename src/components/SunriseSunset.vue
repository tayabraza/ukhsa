<template>
    <div class="weather-card sunrise-sunset" v-if="sunTimes?.sunrise">
      <p>Sunrise: {{ sunTimes.sunrise }}</p>
      <p>Sunset: {{ sunTimes.sunset }}</p>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    sunTimes: Object
  });
  </script>


  <style scoped>

  .sunrise-sunset{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  p{
    margin: 1rem auto;
    font-size: 1.2rem;
  }
  
  </style>