# Hello, World!

My name is Rafael

Desenvolvedor Geral

## Sobre Mim

Olá! Meu nome é Rafael Antônio. Tenho experiência em criar sites usando HTML, CSS e um pouco de JavaScript, além de desenvolver jogos na plataforma Roblox utilizando Lua. Também tenho conhecimentos básicos em Python.

Estou a procura de um emprego de menor aprendiz que me proporcione minha primeira experiência trabalhando com programação, além de que irei desenvolver novas habilidades e proporcionar minha liberdade financeira.

## Habilidades
![HTML](https://img.shields.io/badge/-HTML-333?style=flat&logo=html5)
![CSS](https://img.shields.io/badge/-CSS-333?style=flat&logo=css3&logoColor=1572B6)
![Lua](https://img.shields.io/badge/-Lua-333?style=flat&logo=lua)
![Python](https://img.shields.io/badge/-Python-333?style=flat&logo=python)
![JavaScript](https://img.shields.io/badge/-JavaScript-333?style=flat&logo=javascript)

## Estatísticas do GitHub

<div>
  <a href="https://github.com/SynthX7">
  <img height="150em" src="https://github-readme-stats.vercel.app/api?username=synthx7&show_icons=false&theme=dark" alt="Estatísticas do GitHub">
  <img height="150em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=synthx7&layout=compact&theme=dark" alt="Linguagens mais usadas">
  </a>
</div>
    
## Contato

Você pode entrar em contato comigo através das seguintes plataformas:

- **Instagram:** [@synthx_7](https://www.instagram.com/synthx_7/)
- **WhatsApp:** [Clique aqui para enviar uma mensagem](https://api.whatsapp.com/send?phone=5516994620899)

name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: artur-debv
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
