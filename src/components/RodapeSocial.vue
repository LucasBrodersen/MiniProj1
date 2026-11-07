<script setup>
const redes = [
  { nome: 'Facebook', url: 'https://www.facebook.com/lucasbrodersenbr', icone: 'fa-brands fa-facebook' },
  { nome: 'GitHub', url: 'https://github.com/LucasBrodersen', icone: 'fa-brands fa-github' },
  { nome: 'LinkedIn', url: 'https://www.linkedin.com/in/lucas-brodersen/', icone: 'fa-brands fa-linkedin' },
]
</script>

<template>
  <footer class="rodape">
    <p>Contactos</p>
    <ul>
      <li v-for="rede in redes" :key="rede.nome">
        <a :href="rede.url" target="_blank" rel="noopener" :aria-label="rede.nome">
          <i :class="rede.icone" aria-hidden="true"></i>
        </a>
      </li>
    </ul>
  </footer>
</template>

<style scoped>
.rodape {
  background: #222;
  color: white;
  text-align: center;
  padding: 1.5rem;
}
ul {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  list-style: none;
  margin: 0;
  padding: 0;
}
a {
  color: white;
  font-size: 1.75rem;
}
a:hover {
  opacity: 0.7;
}
</style>