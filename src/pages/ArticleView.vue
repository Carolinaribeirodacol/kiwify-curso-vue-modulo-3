<template>
  <PageDefault>
    <div class="flex gap-4">
      <button class="btn btn-primary" @click="setArticleTitle('Artigo 1')">Ler Artigo 1</button>
      <button class="btn btn-primary" @click="setArticleTitle('Artigo 2')">Ler Artigo 2</button>
      <button class="btn btn-primary" @click="setArticleTitle('Artigo 3')">Ler Artigo 3</button>
    </div>

    <p>Meu artigo está aqui</p>
  </PageDefault>
</template>

<script setup>
import PageDefault from '@/components/PageDefault.vue'
import { ref } from 'vue'

const titleArticle = ref('Lista de artigos')

function setArticleTitle(title) {
  titleArticle.value = title
}
</script>
