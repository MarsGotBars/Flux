<script setup>
import { ref } from 'vue'
import Trending from '@/components/Scroller/Trending.vue'
import ResultList from '@/components/ResultList/ResultList.vue'
import MovieForm from '@/components/MovieForm/MovieForm.vue'
let data = ref([])
const fetchMovies = async (query) => {
  // trycatch > .then
  try {
    const res = await fetch(
      `http://localhost:8080/search/movie?query=${encodeURIComponent(
        query,
      )}&include_adult=false&language=en-US&page=1`,
    )
    const fetchedData = res.json()
    data.value = fetchedData.results
  } catch(error) {
    console.log(error, "error!")
  }
}
const handleSearch = (query) => {
  fetchMovies(query)
}
console.log(data)

console.log(data.value == '')

handleSearch('minecraft')
</script>

<template>
  <h1>movie<span>ender</span></h1>
  <MovieForm />
  <ResultList v-if="data != ''" :movieData="data" />
  <Trending />
  <Trending inverted />
</template>
