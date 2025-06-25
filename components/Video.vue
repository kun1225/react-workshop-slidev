<template>
  <SlidevVideo
    :controls="controls"
    :autoplay="autoplay"
    :loop="loop"
    :muted="muted"
    w="100%"
    h="90%"
    mt="4"
  >
    <slot />
  </SlidevVideo>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';

defineProps<{
  controls?: boolean;
  autoplay?: boolean;
  loop?: boolean;
  muted?: boolean;
}>();
</script>
