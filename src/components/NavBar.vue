<script setup>
// Recebe a secção ativa e avisa o App quando o utilizador clica noutra
defineProps({ atual: String })
const emit = defineEmits(['mudar'])

const links = [
  { id: 'quem-sou', texto: 'Quem sou eu?' },
  { id: 'o-que-faco', texto: 'O que faço?' },
  { id: 'hobbies', texto: 'Hobbies' },
]
</script>

<template>
  <nav class="navbar">
    <ul>
      <li v-for="link in links" :key="link.id">
        <a
          href="#"
          :class="{ ativo: link.id === atual }"
          @click.prevent="emit('mudar', link.id)"
        >
          {{ link.texto }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  background: #222;
}
ul {
  display: flex;
  gap: 1.5rem;
  list-style: none;
  margin: 0;
  padding: 1rem;
}
a {
  color: white;
  text-decoration: none;
}
a:hover,
a.ativo {
  text-decoration: underline;
}
a.ativo {
  font-weight: bold;
}
</style>
