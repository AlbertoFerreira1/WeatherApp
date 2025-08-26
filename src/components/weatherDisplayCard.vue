<template>
    <div class="wrapper" v-if="weather">
        <div class="card">
            <h2>{{ weather.name }} ({{ weather.sys.country }})</h2>
            <p>Temperature {{ weather.main.temp }}°C</p>
        </div>
    </div>
   <div class="wrapper" v-else>
        <div class="card">
          <p>Something Went Wrong, Check if You Spelled the city name correctly</p>
        </div>
    </div>
</template>

<script setup lang="ts">
defineProps<{
    weather: Record<string, any> | null
}>()
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
