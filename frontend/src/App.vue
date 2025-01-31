<script setup>
import { ref } from 'vue'
import Trending from './components/Scroller/Trending.vue'
import ResultList from './components/ResultList/ResultList.vue'
import Form from './components/Form/Form.vue'
let data = ref([])
const fetchMovies = (query) =>
  fetch(
    `http://localhost:8080/search/movie?query=${encodeURIComponent(
      query,
    )}&include_adult=false&language=en-US&page=1`,
  )
    .then((response) => response.json())
    .then((fetchedData) => {
      data.value = fetchedData.results
    })
    .catch((error) => {
      console.error('Error:', error)
    })
const handleSearch = (query) => {
  fetchMovies(query)
}
handleSearch("minecraft")
</script>

<template>
  <h1>movie<span>ender</span></h1>
  <Form/>
  <ResultList :movieData="data" />

  <Trending />
</template>
