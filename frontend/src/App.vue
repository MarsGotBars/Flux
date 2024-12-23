<script setup>
import { ref } from "vue";
import ToggleBtn from './components/toggleBtn/ToggleBtn.vue'
import Trending from "./components/scroller/Trending.vue";
let data = ref([]);
const query = "Inception"; // Example query
fetch(
  `http://localhost:8080/search/movie?query=${encodeURIComponent(
    query
  )}&include_adult=false&language=en-US&page=1`
)
  .then((response) => response.json())
  .then((fetchedData) => {
    console.log(fetchedData); // Handle the search results
    data.value = fetchedData.results; // Assign the results to the reactive data variable
  })
  .catch((error) => {
    console.error("Error:", error); // Handle any errors
  });
</script>

<template>
    <h1>movie<span>ender</span></h1>
  <ToggleBtn label="test" initValue="value1" secondaryValue="value2" />
  <ul v-if="data">
    <li v-for="(item, index) in data" :key="index">{{ item }}</li>
  </ul>
  <Trending />
</template>
