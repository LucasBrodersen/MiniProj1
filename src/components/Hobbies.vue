<script setup>
// Cada hobby tem um título e uma descrição
const hobbies = [
  {
    titulo: 'Ténis',
    descricao: 'Jogo regularmente e gosto de melhorar a minha técnica e estratégia.',
  },
  {
    titulo: 'Magic: The Gathering',
    descricao:
      'Sou fã de jogos de cartas colecionáveis, especialmente Commander. Também desenvolvo um projeto pessoal relacionado com plataformas online para jogar TCGs.',
  },
  {
    titulo: 'Tecnologia e projetos pessoais',
    descricao:
      'Gosto de experimentar novas tecnologias, inteligência artificial, automação e desenvolver pequenos projetos por iniciativa própria.',
  },
  {
    titulo: 'Robótica e gaming',
    descricao:
      'Mantenho o interesse por tecnologia, jogos e projetos que envolvam criatividade e engenharia.',
  },
  {
    titulo: 'Animais e natureza',
    descricao:
      'Gosto de passear, explorar novos lugares e passar tempo com a minha cadela, Kinda.',
  },
]
</script>

<template>
  <section class="hobbies">
    <h2>Hobbies e interesses</h2>

    <p>
      Fora do ambiente profissional, gosto de atividades que me desafiem e me
      permitam aprender coisas novas.
    </p>

    <ul>
      <li v-for="hobby in hobbies" :key="hobby.titulo">
        <strong>{{ hobby.titulo }}:</strong> {{ hobby.descricao }}
      </li>
    </ul>
  </section>
</template>

<style scoped>
section {
  max-width: 900px;
  margin: 0 auto;
  padding: 2rem 1rem;
}
li {
  margin-bottom: 0.75rem;
}
</style>
