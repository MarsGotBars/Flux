<script setup>
defineProps({
  label: String,
  primaryValue: String,
  secondaryValue: String,
})
</script>

<template>
  <label class="sm">
    {{ label }}
    <button type="button">
      <div><span>{{ primaryValue }}</span> <span>{{ secondaryValue }}</span></div>
    </button>
  </label>
</template>

<style scoped>

button{
  display: block;
  border: none;
}
div{
  span{
  background: red;
  }  
}
</style>
