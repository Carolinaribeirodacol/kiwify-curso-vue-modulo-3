<template>
  <div class="card bg-base-100 w-96 shadow-sm mt-10">
    <div class="card-body">
      <h2 class="card-title">Cadastro simples</h2>

      <fieldset class="fieldset">
        <legend class="fieldset-legend">Nome</legend>
        <input type="text" class="input w-full" placeholder="Digite seu nome" v-model="name" />
      </fieldset>

      <fieldset class="fieldset">
        <legend class="fieldset-legend">Idade</legend>
        <input type="text" class="input w-full" placeholder="Digite sua idade" v-model="age" />
      </fieldset>

      <pre>
        {{ name }} - {{ age }} anos
      </pre>

      <div class="card-actions justify-end">
        <button class="btn btn-primary" @click="sendForm">Cadastrar</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const emit = defineEmits(['sendForm'])

const name = defineModel('name', { type: String })
const age = defineModel('age', { type: Number })

function sendForm() {
  emit('sendForm')
}
</script>
