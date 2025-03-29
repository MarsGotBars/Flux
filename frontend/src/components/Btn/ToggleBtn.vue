<script setup>
const props = defineProps({
  label: {
    type: String,
    default: 'Unlabeled',
  },
  choices: {
    type: Array,
    default: [],
  },
})
</script>
<template>
  <label class="btn">
    {{ label }}
    <input type="checkbox" name="" />
    <div class="container">
      <template v-for="(choice, index) in choices" :key="index">
        <p>{{ choice }}</p>
      </template>
    </div>
  </label>
</template>

<style scoped>
label.btn {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: unset;
  max-width: unset;
  cursor: pointer;
}

input {
  appearance: none;
}

.container {
  display: flex;
  height: 100%;
  max-height: 5rem;
  border-radius: 1.125rem;
  align-items: center;
  background: var(--black);
  gap: 0.1875rem;
  position: relative;
  overflow: hidden;
}

.container p {
  padding: 0 1.5rem;
  z-index: 2;
}

.container::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  height: 100%;
  width: 100%;
  transition: 0.3s cubic-bezier(0.785, 0.135, 0.15, 0.86);
  border-radius: .75rem;
  transform: translateX(-50%);
}

input:focus + .container,
input:focus-within + .container {
  outline: var(--important) solid 5px;
}

input + .container::after {
  background-color: var(--pink);
}

label input:checked + .container::after {
    transform: translateX(50%);
}
/* not a perfect implementation */

label:hover input + .container::after {
    transform: translateX(-50%) scaleX(1.1);
}

label:hover input:checked + .container::after {
    transform: translateX(50%) scaleX(1.1);
}

input:focus + .container::after{
    transform: translateX(-50%) scaleX(1.1);
}

input:checked:focus + .container::after{
    transform: translateX(50%) scaleX(1.1);
}

p{
    text-transform: uppercase;
    text-wrap: nowrap;
}
</style>
