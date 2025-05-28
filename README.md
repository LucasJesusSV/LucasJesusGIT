Olá, Tudo Bem sou Lucas De Jesus .

# 👨‍💻 Aprendendo JavaScript

Bem-vindo ao meu repositório! Aqui estou registrando minha jornada de aprendizado em **JavaScript**, compartilhando códigos, exercícios, desafios e projetos simples que venho desenvolvendo.

---

## 🎯 Objetivo

Sou estudante e criei este espaço para:

- Praticar conceitos fundamentais da linguagem JavaScript 🟨  
- Organizar meus códigos e estudos de forma pública 🗂️  
- Acompanhar minha evolução 📈  
- Compartilhar conhecimento com outras pessoas que também estão aprendendo 🤝

---

## 🧠 O que você vai encontrar aqui?

- 🧪 Exercícios básicos e intermediários  
- 🕹️ Mini projetos em HTML, CSS e JS  
- 💡 Anotações e comentários no código  
- 🔄 Atualizações frequentes conforme avanço nos estudos  

---

## 🛠 Tecnologias

Este repositório será focado principalmente em:

- **JavaScript (puro)**
- **HTML5**
- **CSS3**

---

## 📬 Contato

Se quiser trocar ideias ou dicas sobre programação, fique à vontade para me chamar:

- 💼 [Meu LinkedIn](www.linkedin.com/in/lucas-de-jesus-da-silva-0464b8352)
- 📧 [Meu Gmail](dasilvadejesuslucas23@gmail.com)

---

📌 _Este repositório será constantemente atualizado conforme avanço nos estudos._

<div style="display: inline_block"><br>
<img align="center" alt="BootCamp-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
[<img align="center" alt="BootCamp-Python" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg">]
<img align="center" alt="BootCamp-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="BootCamp-CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
</div>

 ##

 </div>
 <a href="https://instagram.com/_lluquinnhas_" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
<a href="https://www.linkedin.com/in/Lucas de Jesus da Silva" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  </div>
  *name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}*
