<script setup>
// API call to receive daily trending movie
// only make the call if the daily value has not been cached
// and only make the cache last 24 hours or check if it is a new day
</script>

<template>
  <article>
    <p>
      Trending<span> - </span><a href="">Movie</a> <span> - </span>Trending<span> - </span
      ><a href="">Movie</a><span> - </span> Trending
    </p>
  </article>
  <article>
    <p>
      Trending<span> - </span><a href="">Movie</a> <span> - </span>Trending<span> - </span
      ><a href="">Movie</a><span> - </span> Trending
    </p>
  </article>
</template>

<!-- incorrect... retry -->
<style lang="css" scoped>
article {
  position: fixed;
  left: 0;
  top: 0;
  width: calc(4rem / 100 * 80);
  height: var(--spacing-xl);
  rotate: 90deg;
  display: flex;
  align-items: center;
  line-height: 1;
  will-change: transform;
  &:nth-of-type(2){
    right: 0;
  }
}
p {
  font-weight: 500;
  > * {
    font-weight: 500;
    line-height: 80%;
  }
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
    transform: translateX(-10%);
  }
  to {
    transform: translateX(-50%);
  }
}
</style>
