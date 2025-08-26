<script setup lang="ts">
import Banner from './components/banner.vue';
import WeatherSearch from './components/weatherSearch.vue';

</script>

<template>
  <div class="app">
      <Banner></Banner>
      <hr></hr>
    <WeatherSearch></WeatherSearch>
  </div>
</template>

<style scoped>
.app {
  background-color: beige;
}
</style>
