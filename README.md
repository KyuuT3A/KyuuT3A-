## 🛠️ My Tech Stack

<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/TSQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white"/>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white"/>
  <img src="https://img.shields.io/badge/Visual_Basic_.NET-512BD4?style=for-the-badge&logo=.net&logoColor=white"/>
</div>

<div align="center">
  <img src="https://media.giphy.com/media/LMt9638dO8dftAjtco/giphy.gif" width="60"/>
  <img src="https://media.giphy.com/media/ln7z2eWriiQAllfVcn/giphy.gif" width="60"/>
  <img src="https://media.giphy.com/media/XAxylRMCdpbEWUAvr8/giphy.gif" width="60"/>
</div>

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 0 * * *" # Runs at 00:00 UTC every day
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: KyuuT3A
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
