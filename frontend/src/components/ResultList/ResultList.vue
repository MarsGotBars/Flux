<script setup>
import { watch, onMounted } from 'vue';
import Result from '../Result/Result.vue';

const props = defineProps({
  movieData: Array,
});

onMounted(() => {
  console.log('movieData in onMounted:', props.movieData); // Check if movieData is passed correctly
});

watch(() => props.movieData, (newVal) => {
  console.log('movieData changed:', newVal); // Watch for changes in movieData
});
</script>

<template lang="">
  <section v-if="props.movieData && props.movieData.length">
    <h2>Total Results: {{ props.movieData.length }}</h2>
    <ul>
      <Result :movieData="props.movieData" />
    </ul>
  </section>
  <p v-else>No movies available.</p>
</template>
