<script setup>
import { onMounted, watch } from 'vue'

const props = defineProps({
  items: {
    type: Array,
    default: () => [], // Only default value, not required
  },
})

onMounted(() => {
  console.log('movieData in Result:', props) // Check if movieData is passed correctly
})

watch(
  () => props,
  (newVal) => {
    console.log('movieData changed:', newVal) // Watch for changes in movieData
  },
)
</script>

<template>
  <li v-for="(item, index) in items" :key="item.id || index">
    <h3>{{ item.title }}</h3>
  </li>
</template>
