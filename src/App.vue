<script setup>
import { ref } from 'vue'
import NavBar from './components/NavBar.vue'
import QuemSou from './components/QuemSou.vue'
import OQueFaco from './components/OQueFaco.vue'
import Hobbies from './components/Hobbies.vue'
import RodapeSocial from './components/RodapeSocial.vue'

// Guarda qual é a secção que está a ser mostrada neste momento
const seccaoAtual = ref('quem-sou')
</script>

<template>
  <NavBar :atual="seccaoAtual" @mudar="seccaoAtual = $event" />

  <main>
    <QuemSou v-if="seccaoAtual === 'quem-sou'" />
    <OQueFaco v-else-if="seccaoAtual === 'o-que-faco'" />
    <Hobbies v-else-if="seccaoAtual === 'hobbies'" />
  </main>

  <RodapeSocial />
</template>
