<script setup>
import { onMounted, watch } from 'vue'

const props = defineProps({
  items: {
    type: Array,
    default: () => [],
  },
})

onMounted(() => {
  console.log('movieData in Result:', props)
})

watch(
  () => props,
  (newVal) => {
    console.log('movieData changed:', newVal)
  },
)
</script>

<template>
  <li v-for="(item, index) in items" :key="item.id || index">
    <h3>{{ item.title }}</h3>
  </li>
</template>
