<template>
  <PageDefault :pageTitle="`Home Page ${count}`">
    <div>
      <button class="btn btn-primary" @click="count++">Count +1</button>
    </div>

    <p>Conteúdo aqui de teste</p>
  </PageDefault>
</template>

<script setup>
import PageDefault from '@/components/PageDefault.vue'
import { ref } from 'vue'

const count = ref(1)
</script>
