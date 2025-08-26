<template>
  <div class="banner">
    <div class="banner-content">
      <h1>Weather App</h1>
    </div>
  </div>
</template>

<script setup>
// You can pass props if you want later, like image url or title
</script>

<style scoped>
.banner {
  height: 25vh !important;
  width: 100%;
  background-image: url('https://images.unsplash.com/photo-1501973801540-537f08ccae7b'); /* replace with your own */
  background-size: cover; /* image covers full area */
  background-position: center; /* center the image */
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}

.banner-content {
  text-align: center;
  background: rgba(0, 0, 0, 0.4); /* optional dark overlay */
  padding: 2rem;
  border-radius: 12px;
}

.banner h1 {
  font-size: 4rem;
  font-weight: bold;
  margin: 0;
}
</style>
