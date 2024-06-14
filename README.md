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

# GitHub Action for generating a contribution graph with a snake eating your contributions.

# ![snake gif](https://github.com/your-user-name/your-user-name/blob/output/github-contribution-grid-snake.gif)

name: Generate Snake

# Controls when the action will run.
on:
  schedule:
      # every 12 hours
    - cron: "0 */12 * * *"

  # This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:
  
  # Also run on every push on the master branch
  push:
    branches:
    - main

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

   # Steps represent a sequence of tasks that will be executed as part of the job
  steps:
      - name: Clone repo
        uses: actions/checkout@v3
          - name: Generate the snake files in './dist/'
        uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |     
            dist/github-contribution-grid-snake.gif
            dist/github-contribution-grid-snake.svg
        env:
           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

   - name: Show build status
        run: git status

      - name: Push new files to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
          commit_message: Update snake animations
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }
