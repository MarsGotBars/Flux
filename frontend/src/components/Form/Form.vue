<script setup>
import ToggleBtn from './ToggleBtn/ToggleBtn.vue'
import Search from './Search/Search.vue'
</script>
<template lang="">
  <section>
    <h2 class="lg">Catching a movie? Find out when it ends!</h2>
    <form>
      <Search />
      <ToggleBtn label="test" primaryValue="value1" secondaryValue="value2" />
      <ToggleBtn label="test" primaryValue="value1" secondaryValue="value2" />
      <ToggleBtn label="test" primaryValue="value1" secondaryValue="value2" />
    </form>
  </section>
</template>

<style scoped>
form {
  gap: clamp(0.5rem, 2vw, var(--spacing-sm));
  border-radius: 1.125rem;
  display: flex;
  flex-direction: row;
  padding: 0.375rem 1rem;
  background: var(--white);
  label,
  &:deep(label) {
    gap: 0.625rem;
    display: flex;
    flex-direction: column;
    &:has(input[type='search']) {
      cursor: text;
    }
    &:deep(input) {
        font-family: var(--alt-font);
      border: none;
      caret-color: var(--white);
      color: var(--white);
      padding: var(--spacing-sm) 2rem;
      border-radius: 1.125rem;
      font-size: var(--spacing-sm);
      background: var(--black);
      text-align: left;
    }
  }
}
</style>
