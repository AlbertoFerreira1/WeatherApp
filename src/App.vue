<script setup lang="ts">
import { ref } from 'vue';
import Banner from './components/banner.vue';
import WeatherSearch from './components/weatherSearch.vue';
import WeatherDisplayCard from './components/weatherDisplayCard.vue';


const weatherData = ref(null)

function handleWeather(data : any) {
  weatherData.value = data
}
</script>

<template>
  <div class="app">
      <Banner></Banner>
      <hr></hr>
    <WeatherSearch @weather-fetched="handleWeather"></WeatherSearch>
    <WeatherDisplayCard :weather="weatherData"></WeatherDisplayCard>
  </div>
</template>

<style scoped>
.app {
  background-color: beige;
  height: max-content ;
}
</style>
