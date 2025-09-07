<template>
  <div class="wrapper" v-if="weather">
    <div class="card">
      <h2>{{ weather.name }} ({{ weather.sys.country }})</h2>
      <p>Temperature {{ weather.main.temp }}°C</p>
      <p>Max Temperature for the day {{ weather.main.temp_max }}</p>
      <p>Min Temperature for the day {{ weather.main.temp_min }}</p>
    
<br></br>
      <div v-if="weatherDescription" class="advice">
        <weather-advice :description="weatherDescription" />
      </div>
    </div>
  </div>

  <div class="wrapper" v-else></div>
</template>

<script setup lang="ts">
import { computed } from 'vue';
import weatherAdvice from './weatherAdvice.vue';
const props = defineProps<{
    weather: Record<string, any> | null
}>()

const weatherDescription = computed(() => {
  if (!props.weather || !props.weather.weather || props.weather.weather.length === 0) {
    return "Unknown weather";
  } else {
    return props.weather.weather[0].description;
  }
})

</script>

<style scoped>
.wrapper {
    padding: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50vh;
}

.card {
    width: 33%;
    background: beige;
    padding: 20px;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
</style>
