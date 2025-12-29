<template>
  <div class="p-10">
    <h1 class="text-2xl text-secondary flex justify-between">
      {{ pageTitle || '' }}
      <button class="btn btn-primary btn-outline" @click="setRefresh()">Refresh</button>
    </h1>

    <div class="mt-4">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
const emit = defineEmits(['refresh'])

defineProps({
  pageTitle: {
    type: String,
    default: 'Title page',
  },
})

function setRefresh() {
  emit('refresh')
}
</script>
