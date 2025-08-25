
### Olá! Eu sou o Davi Bianchi👋

[![Linkedln](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/davi-bianchi-ayres-656783356/)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white
)](https://www.instagram.com/davi_bianchiayres/)

---

<h3 align=>📊 Minhas estatísticas</h3>
<p align=>
  <img 
    height="160" 
    src="https://github-readme-stats.vercel.app/api/top-langs/?username=Davibianchi01&theme=tokyonight&layout=compact&custom_title=Linguagens&langs_count=9" 
  />
</p>


name: Generate Snake Animation

on:
  schedule:
    - cron: "0 0 * * *"  
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: GeovanaBlasius
          outputs: dist/github-contribution-grid-snake.svg
      - name: Upload artifact
        uses: actions/upload-artifact@v3
        with:
          name: snake
          path: dist/github-contribution-grid-snake.svg
      - name: Push to output branch
        uses: EndBug/add-and-commit@v9
        with:
          branch: output
          message: "Generate snake animation"
          add: "dist/*.svg"

