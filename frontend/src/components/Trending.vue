<script setup>
// API call to receive daily trending movie
// only make the call if the daily value has not been cached
// and only make the cache last 24 hours or check if it is a new day
</script>

<template>
  <article>
    <p>
      Trending<span> - </span><a href="">Movie</a> <span> - </span>Trending<span> - </span><a href="">Movie</a><span> - </span>
    </p>
  </article>
</template>

<!-- incorrect... retry -->
<style scoped>
article {
  position: fixed;
  left: -1%;
  top: 0%;
  width: 72px;
  height: var(--spacing-xl);
  rotate: 90deg;
  display: flex;
  align-items: center;
  line-height: 1;
}
p {
  display: inline-block;
  text-wrap: nowrap;
  color: var(--gray);
  text-transform: uppercase;
  font-size: var(--spacing-xl);
  /* rotates */
  /* transform: rotate(90deg); */
  /* placeholder value until I find a better way of rotating */
  span {
    color: var(--gray);
  }
  a {
    color: var(--pink);
  }
  animation: scroller 5s linear infinite;
}
@keyframes scroller {
  from {
    transform: translateX(0%);
  }
  to{
    transform: translateX(-50%);
  }
}
</style>
