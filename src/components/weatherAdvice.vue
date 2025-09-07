<template>
  <div>
    <p>{{ weatherAdvice }}</p>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  description: string | null
}>()

const weatherAdvice = computed(() => {
  if (!props.description) return 'No weather description available.'

  const desc = props.description.toLowerCase()

  if (desc.includes('clouds')) {
    return 'It’s going to be cloudy. The weather is not very nice, take a jacket if you are leaving your house at night.'
  } else if (desc.includes('rain')) {
    return 'Looks like rain! Don’t forget your umbrella.'
  } else if (desc.includes('sun')) {
    return 'Sunny skies ahead! Perfect day to go outside.'
  } else if (desc.includes('snow')) {
    return 'Snowy conditions expected. Dress warmly and be careful on the roads.'
  }

  return 'Weather looks fine, have a good day!'
})
</script>
