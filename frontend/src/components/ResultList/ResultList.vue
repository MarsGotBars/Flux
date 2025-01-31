<script setup>
import { watch, onMounted } from 'vue'
import Result from '../Result/Result.vue'

// Better prop definition with validation and types
const props = defineProps({
  movieData: {
    type: Array,
    default: () => [], // Only default value, not required
  },
})

// Watch can be simplified since we're not using the callback much
watch(
  () => props.movieData,
  () => {
    console.log('movieData changed:', props.movieData)
  },
)
</script>

<template>
  <!-- No need for props. in template -->
  <section v-if="movieData && movieData.length">
    <h2 class="lg"><span>{{ movieData.length }}</span> Results</h2>
    <ul>
      <!-- Pass only the items that Result needs -->
      <!-- move result LI to here -->
      <Result :items="movieData" />
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

ul{
  display: flex;
}
</style>
