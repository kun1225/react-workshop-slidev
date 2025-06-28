<template>
  <div
    ref="container"
    class="h-full grow flex flex-col justify-center"
    :style="{ height: `${centerHeight}px` }"
  >
    <slot />
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick } from 'vue';

const container = ref(null);
const centerHeight = ref(0);

onMounted(async () => {
  await nextTick();

  const containerEl = container.value;
  const parentEl = containerEl.parentElement;

  const parentStyle = getComputedStyle(parentEl);

  const parentHeight = parentEl.offsetHeight;

  const paddingTop = parseFloat(parentStyle.paddingTop);
  const paddingBottom = parseFloat(parentStyle.paddingBottom);
  const totalPadding = paddingTop + paddingBottom;

  const siblings = Array.from(parentEl.children).filter(
    child => child !== containerEl
  );
  const siblingsHeight = siblings.reduce((total, sibling) => {
    return total + sibling.offsetHeight;
  }, 0);

  centerHeight.value = parentHeight - siblingsHeight - totalPadding;

  containerEl.style.height = `${centerHeight.value}px`;
});
</script>
