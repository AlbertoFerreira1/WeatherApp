<template>
  <div class="wrapper">
  <div class="Card">
    <input
      class="searchCard"
      type="search"
      placeholder="Search City"
      v-model="citySearch"
      @keyup.enter="fetchWeather"
    />
  </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
const emit = defineEmits(['weather-fetched'])

const citySearch = ref('')

async function fetchWeather() {
  if (!citySearch.value) return
  console.log('Fetching weather for:', citySearch.value)

  try {
    const res = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?q=${citySearch.value}&appid=aa2b0748e2876d0b463ca2b19cf1f69c&units=metric`
    )
    if (!res.ok) throw new Error('City not found')
    const data = await res.json();
     emit('weather-fetched', data);
    console.log('Weather:', data)
  } catch (err) {
    console.error(err.message)
  }
}
</script>


<style>
.wrapper {
  display: flex;
  justify-content: center; 
  align-items: center;    
         
}

.searchCard{
  padding: 5px;
   display: flex;
  border-radius: 10px;
}

.Card{
    margin-top: 25px;
    background-color: beige;
}
</style>