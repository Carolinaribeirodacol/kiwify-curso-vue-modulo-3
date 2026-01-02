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

      <BasicForm v-model:name="form.name" v-model:age="form.age" @sendForm="sendForm" />

      <span> Form externo homeview </span>

      <pre>
        {{ form }}
      </pre>
    </div>
  </PageDefault>
</template>

<script setup>
import { defineAsyncComponent, ref } from 'vue'

const PageDefault = defineAsyncComponent(() => {
  import('@/components/PageDefault.vue')
})

const BasicForm = defineAsyncComponent(() => {
  import('@/components/BasicForm.vue')
})

const count = ref(1)
const loading = ref(false)

const form = ref({
  name: '',
  age: 0,
})

function handleGetAPI() {
  loading.value = true

  setTimeout(() => {
    loading.value = false
  }, 2000)
}

function sendForm() {
  alert('Form enviado')
}
</script>
