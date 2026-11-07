<script setup>
import { onMounted, onUnmounted } from 'vue'

defineProps({
  aberto: Boolean,
  titulo: String,
})

const emit = defineEmits(['fechar'])

function aoPremirTecla(e) {
  if (e.key === 'Escape') emit('fechar')
}

onMounted(() => window.addEventListener('keydown', aoPremirTecla))
onUnmounted(() => window.removeEventListener('keydown', aoPremirTecla))
</script>

<template>
  <div v-if="aberto" class="fundo" @click.self="emit('fechar')">
    <div class="caixa" role="dialog" aria-modal="true" :aria-label="titulo">
      <button class="fechar" aria-label="Fechar" @click="emit('fechar')">×</button>
      <h3 v-if="titulo">{{ titulo }}</h3>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.fundo {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.6);
  display: grid;
  place-items: center;
  z-index: 100;
}
.caixa {
  position: relative;
  background: white;
  padding: 2rem;
  border-radius: 8px;
  max-width: 500px;
  width: calc(100% - 2rem);
}
.fechar {
  position: absolute;
  top: 0.5rem;
  right: 0.75rem;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
}
</style>