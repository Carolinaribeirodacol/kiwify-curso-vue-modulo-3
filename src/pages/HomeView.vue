<template>
  <PageDefault :pageTitle="`Home Page ${count}`" @refresh="handleGetAPI">
    <div v-if="loading" class="text-center">
      <span class="loading loading-spinner loading-xl"></span>
    </div>

    <div v-else>
      <div>
        <button class="btn btn-primary" @click="count++">Count +1</button>
      </div>

      <p>Conteúdo aqui de teste</p>
    </div>
  </PageDefault>
</template>

<script setup>
import PageDefault from '@/components/PageDefault.vue'
import { ref } from 'vue'

const count = ref(1)
const loading = ref(false)

function handleGetAPI() {
  loading.value = true

  setTimeout(() => {
    loading.value = false
  }, 2000)
}
</script>
