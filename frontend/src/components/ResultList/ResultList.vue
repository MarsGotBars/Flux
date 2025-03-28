<script setup>
import { watch, onMounted } from 'vue'
import ResultItems from '../ResultItems/ResultItems.vue'

const props = defineProps({
  movieData: {
    type: Array,
    default: () => [],
  },
})
watch(
  () => props.movieData,
  () => {
    console.log('movieData changed:', props.movieData)
  },
)
</script>

<template>
  <section v-if="movieData && movieData.length">
    <h2 class="lg"><span>{{ movieData.length }}</span> Results</h2>
    <ul>
      <ResultItems :items="movieData" />
    </ul>
  </section>
  <p v-else>No movies available.</p>
</template>

<style scoped>
h2 {
  span {
    color: var(--pink);
    font-weight: 500;
  }
}
</style>
