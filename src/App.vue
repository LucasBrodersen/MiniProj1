<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import NavBar from './components/NavBar.vue'
import QuemSou from './components/QuemSou.vue'
import OQueFaco from './components/OQueFaco.vue'
import Hobbies from './components/Hobbies.vue'
import RodapeSocial from './components/RodapeSocial.vue'

const seccoes = ['quem-sou', 'o-que-faco', 'hobbies']

// Lê o hash do URL (por exemplo #hobbies). Se for inválido ou vazio, mostra "quem-sou"
function lerSeccaoDoUrl() {
  const id = window.location.hash.slice(1)
  return seccoes.includes(id) ? id : 'quem-sou'
}

// Guarda qual é a secção que está a ser mostrada neste momento
const seccaoAtual = ref(lerSeccaoDoUrl())

// Atualiza a secção sempre que o hash muda (clique no menu ou botão "Voltar")
function aoMudarHash() {
  seccaoAtual.value = lerSeccaoDoUrl()
}

onMounted(() => window.addEventListener('hashchange', aoMudarHash))
onUnmounted(() => window.removeEventListener('hashchange', aoMudarHash))
</script>

<template>
  <header class="cabecalho">
    <h1>Lucas Brodersen</h1>
    <p>Development Lead · Mestrando em Engenharia Informática e Tecnologia Web</p>
  </header>

  <NavBar :atual="seccaoAtual" />

  <main>
    <QuemSou v-if="seccaoAtual === 'quem-sou'" />
    <OQueFaco v-else-if="seccaoAtual === 'o-que-faco'" />
    <Hobbies v-else-if="seccaoAtual === 'hobbies'" />
  </main>

  <RodapeSocial />
</template>

<style scoped>
.cabecalho {
  text-align: center;
  padding: 2rem 1rem 1.5rem;
}
.cabecalho h1 {
  margin: 0;
}
.cabecalho p {
  margin: 0.25rem 0 0;
  color: #555;
}
</style>
