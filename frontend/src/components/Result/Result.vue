<script setup>
import { onMounted, watch } from 'vue';

const props = defineProps({
  movieData: Array,
});

onMounted(() => {
  console.log('movieData in Result:', props); // Check if movieData is passed correctly
});

watch(() => props, (newVal) => {
  console.log('movieData changed:', newVal); // Watch for changes in movieData
});
</script>

<template lang="">
  <li v-for="(item, index) in props.movieData" :key="index">
    {{ item.title }}
  </li>
</template>
