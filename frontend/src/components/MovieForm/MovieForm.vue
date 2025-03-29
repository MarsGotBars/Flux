<script setup>
import ToggleBtn from '../Btn/ToggleBtn.vue'
import TimeSelector from '../Btn/TimeSelector.vue';
const { time, location } = {
  time: ['AM', 'PM'],
  location: ['Cinema', 'At home'],
}
</script>

<template>
  <form action="" method="get">
    <label class="search">
      Movie
      <input type="search" name="" id="" />
    </label>
    <TimeSelector/>
    <ToggleBtn label="Time" :choices="time" />
    <ToggleBtn label="Location" :choices="location" />
  </form>
</template>

<style scoped>
form {
  display: flex;
  gap: 1rem;
  height: 8.125rem;
  border-radius: 1.125rem;
  padding: 0.375rem 1rem;
  gap: 1.5rem;
  background: var(--white);
}

label.search {
  
  width: 100%;
  max-width: 620px;
}

label{
  font-size: var(--spacing-sm);
  font-weight: 700;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

form > label * {
  font-size: inherit;
  font-weight: 600;
  font-family: var(--alt-font);
  color: #f5f5f5;
  color: var(--white);
}

form input:focus{
    transition: .3s ease;
    outline: var(--important) solid 5px;
}

input[type='search'] {
border: none;
  border-radius: 1.125rem;
  background: var(--black);
  height: 5rem;
  padding: 0 2rem;
  color: var(--gray);
}

/* cancel button uitvergroten
nog even kijken of dit op de een of 
andere manier groter kan */
::-webkit-search-cancel-button{
    padding: .25rem;
    cursor: pointer;
}

</style>
