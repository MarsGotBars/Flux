<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (CSS.supports('--property: value')) {
    const label = document.querySelector('label.startTime')
    label.style.setProperty('--display', 'none')
  }
})
</script>

<template>
  <label class="startTime" for="">
    Start time
    <div class="container">
      <div class="wrapper">
        <button class="upper">+</button>
        <input type="number" name="" id="" value="12" />
        <button class="downer">-</button>
      </div>
      :
      <div class="wrapper">
        <button class="upper">+</button>
        <input type="number" name="" id="" value="12" />
        <button class="downer">-</button>
      </div>
    </div>
  </label>
</template>

<style scoped>
label.startTime {
  --display: inline-block;
  width: fit-content;
  text-wrap: nowrap;
}
.container button {
  font-size: 1.25rem;
  background: var(--pink);
  color: var(--white);
  border: none;
  cursor: pointer;
  z-index: 2;
}

.container {
  height: 5rem;
  display: flex;
  align-items: center;
  color: var(--pink);
}

.wrapper {
  background: var(--black);
  height: 100%;
  display: flex;
  flex-direction: column;
  width: 5.875rem;
  min-height: 5rem;
  border-radius: 1.125rem;
  overflow: hidden;
  position: relative;
}

@supports selector(::after) {
  .container button {
    background: transparent;
  }

  .wrapper::after,
  .wrapper::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: var(--pink);
    transform: translateY(calc(-100% + 1.25rem));
    z-index: 1;
    border-radius: 0 0 1.125rem 1.125rem;
    transition: 0.3s cubic-bezier(0.785, 0.135, 0.15, 0.86);
  }

  .wrapper::before {
    transform: translateY(calc(100% - 1.25rem));
    border-radius: 1.125rem 1.125rem 0 0;
  }

  .wrapper:hover:has(button.upper:hover)::after {
    transform: translateY(-65%);
  }

  .wrapper:hover:has(button.downer:hover)::after {
    transform: translateY(calc(-150% + 1.25rem));
  }

  .wrapper:hover:has(button.downer:hover)::before {
    transform: translateY(65%);
  }

  .wrapper:hover:has(button.upper:hover)::before {
    transform: translateY(calc(150% - 1.25rem));
  }
}

.wrapper button.downer {
  border-radius: 1.125rem 1.125rem 0 0;
}

.wrapper button.upper {
  border-radius: 0 0 1.125rem 1.125rem;
}

input {
  width: auto;
  height: 100%;
  text-align: center;
  border: none;
  height: 3rem;
  background: transparent;
  z-index: 3;
}

::-webkit-inner-spin-button {
  display: var(--display);
}
</style>
