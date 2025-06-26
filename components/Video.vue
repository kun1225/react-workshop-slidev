<template>
  <SlidevVideo
    :controls="props.controls"
    :autoplay="props.autoplay"
    :loop="props.loop"
    :muted="props.muted"
    w="100%"
    h="90%"
    mt="4"
  >
    <slot />
  </SlidevVideo>
</template>

<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    controls?: boolean;
    autoplay?: boolean;
    loop?: boolean;
    muted?: boolean;
  }>(),
  {
    controls: true,
    autoplay: false,
    loop: false,
    muted: false,
  }
);
</script>
