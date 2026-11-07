# MiniProj1

A minha página pessoal, feita como SPA (Single Page Application) com Vue.js.
É uma única página que muda de secção sem recarregar, com um menu no topo e os
meus contactos sempre visíveis no rodapé.

## O que tem

- **Quem sou eu?** — uma apresentação minha
- **O que faço?** — o meu trabalho e as tecnologias que uso
- **Hobbies e interesses** — o que gosto de fazer fora do trabalho
- **Rodapé** com ligações para o Facebook, GitHub e LinkedIn

A secção atual fica no endereço (por exemplo `#hobbies`), por isso o botão
"Voltar" do browser funciona como esperado.

## Como correr

Precisas de Node.js `^22.18` ou `>=24.12`.

```bash
npm install
npm run dev
```

Depois abre <http://localhost:5173> no browser.

Para gerar a versão final, usa `npm run build`. Os ficheiros ficam na pasta `dist/`.

## Estrutura

```
src/
├── App.vue                  # junta tudo e decide que secção mostrar
├── main.js
├── assets/main.css          # estilos globais
└── components/
    ├── NavBar.vue           # menu com os links internos
    ├── QuemSou.vue
    ├── OQueFaco.vue
    ├── Hobbies.vue
    └── RodapeSocial.vue     # ícones das redes sociais
docs/wireframes/             # esboços das páginas
```

## Wireframes

Os esboços das páginas estão em [`docs/wireframes`](docs/wireframes/README.md).

## Feito com

[Vue 3](https://vuejs.org/), [Vite](https://vite.dev/) e [Font Awesome](https://fontawesome.com/) (ícones).

## Autor

Lucas Brodersen — [GitHub](https://github.com/LucasBrodersen) · [LinkedIn](https://www.linkedin.com/in/lucas-brodersen/)
