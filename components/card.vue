<template>
  <div class="card px-2 py-12 rounded-lg bg-[var(--card-background)] shadow-lg">
    <header
      v-if="$slots.header"
      class="mb-6 text-xl text-center text-primary font-semibold"
    >
      <slot name="header" />
    </header>

    <div class="whitespace-wrap px-4">
      <slot name="default" />
    </div>
  </div>
</template>

<script setup lang="ts"></script>
