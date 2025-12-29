<template>
  <div class="p-10">
    <h1 class="text-2xl text-secondary">
      {{ pageTitle || '' }}
    </h1>

    <div class="mt-4">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  pageTitle: {
    type: String,
    default: 'Title page',
  },
})
</script>
