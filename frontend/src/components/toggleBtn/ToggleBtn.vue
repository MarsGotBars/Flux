<script setup>
defineProps({
  label: String,
  initValue: String,
  secondaryValue: String
});
</script>

<template>
  <label>
    {{ label }}
    <button type="button">{{ initValue }} {{ secondaryValue }}</button>
  </label>
</template>

<style scoped>
/* Your styles here */
</style>