<template>
  <div ref="element" :class="{ 'in-view': inView }">
    <slot />
  </div>
</template>
<style lang="less" scoped>

  .in-view {
    opacity: 1;
    transform: translateY(0);
    transition: opacity 1s, transform 0.8s;
  }

  div {
    opacity: 0;
    transform: translateY(20px);
  }
</style>
<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const element = ref(null);
const inView = ref(false);
let observer = null;

onMounted(() => {
  observer = new IntersectionObserver(([entry]) => {
    inView.value = entry.isIntersecting;
  });

  if (element.value) {
    observer.observe(element.value);
  }
});

// onUnmounted(() => {
//   if (element.value) {
//     observer.unobserve(element.value);
//   }
// });
</script>


