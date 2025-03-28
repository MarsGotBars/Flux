<script setup>
// API call to receive daily trending movie
// only make the call if the daily value has not been cached
// and only make the cache last 24 hours or check if it is a new day
const props = defineProps({
  inverted: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <!-- ! conditional inverted class (not working) -->
  <article class="scroller" :class="inverted && 'inverted'">
    <div class="wrapper">
    <p>Trending</p>
    <span>-</span>
    <h2><a href="">Maze runner</a></h2>
    <span>-</span>
    <p>Trending</p>
    <span>-</span>
    <h2><a href="">Maze runner</a></h2>
    <span>-</span>
    <p>Trending</p>
    <span>-</span>
    <h2><a href="">Maze runner</a></h2>
    <span>-</span>
    <p>Trending</p>
    <span>-</span>
    <h2><a href="">Maze runner</a></h2>
    <span>-</span>
  </div>
  </article>
</template>

<!-- Moet nog anders, misschien een wrapper in article -->
<style lang="css" scoped>
.scroller {
  position: fixed;
  top: -2rem;
  left: 0;
  display: flex;
  font-size: var(--spacing-xxl);
  font-weight: 400;
  gap: 0.5ch;
  transform-origin: bottom left;
  rotate: 90deg;
  align-items: center;
  line-height: 0.65;
  text-transform: uppercase;
  white-space: nowrap;
  flex-wrap: nowrap;
  width: 200%;
  animation: ticker 7s linear infinite;
}

.scroller.inverted {
  position: fixed;
  top: calc(100% - 3rem);
  left: 100%;
  rotate: -90deg;
  /* transform-origin: right; */
  /* animation: unset; */
  animation: ticker-inverted 7s linear infinite;
}

.wrapper{
  display: flex;
}

a {
  font-weight: inherit;
  color: inherit;
  transition: 0.5s cubic-bezier(0.19, 1, 0.22, 1);
}

a:hover {
  font-weight: 700;
  color: var(--white);
}

@supports selector(:has(a)) {
  .scroller:has(a:hover) {
    animation-play-state: paused;
  }
}
p,
h2 {
  text-transform: inherit;
  line-height: inherit;
  font-size: inherit;
  font-weight: 500;
}

span {
  color: var(--white);
}

h2 {
  color: var(--gray);
}

@keyframes ticker {
  to {
    transform: translateX(calc(-50% - 3rem));
  }
}

@keyframes ticker-inverted {
  to {
    transform: translateX(calc(-50% - 3rem));
  }
}
</style>
