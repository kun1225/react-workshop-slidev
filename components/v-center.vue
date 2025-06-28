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
import { ref, onMounted, onUnmounted } from 'vue';

const container = ref(null);
const centerHeight = ref(0);
let resizeObserver = null;

const calculateHeight = () => {
  const containerEl = container.value;
  if (!containerEl || !containerEl.parentElement) return;

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
};

onMounted(() => {
  // 延遲計算，確保所有元素都渲染完成
  setTimeout(calculateHeight, 0);

  // 監聽父元素尺寸變化
  if (container.value?.parentElement) {
    resizeObserver = new ResizeObserver(calculateHeight);
    resizeObserver.observe(container.value.parentElement);
  }
});

onUnmounted(() => {
  if (resizeObserver) {
    resizeObserver.disconnect();
  }
});
</script>
