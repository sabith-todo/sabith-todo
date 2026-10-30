<div align="center">

# Hi, I'm Sabith 👋

### AI Engineer in the making · AI Agent Developer · Full-Stack Builder

*I turn ideas into practical, intelligent software and share what I learn along the way.*

<a href="https://github.com/sabith-todo"><img src="https://img.shields.io/badge/GitHub-sabith--todo-181717?style=for-the-badge&logo=github" alt="GitHub"/></a>
<img src="https://img.shields.io/badge/Focus-AI%20%26%20Agents-0EA5E9?style=for-the-badge&logo=openai&logoColor=white" alt="Focus"/>
<img src="https://img.shields.io/badge/Based%20in-Coimbatore%2C%20India-16A34A?style=for-the-badge" alt="Location"/>
<img src="https://komarev.com/ghpvc/?username=sabith-todo&label=Profile%20views&color=0e75b6&style=for-the-badge" alt="Profile views"/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&pause=1200&color=38BDF8&center=true&vCenter=true&width=750&lines=Building+AI-Powered+Applications;Developing+AI+Agents+%26+Automations;Exploring+Generative+AI+%26+LLMs;Full-Stack+Web+Developer" alt="Typing animation"/>

</div>

---

## About

B.Tech Information Technology student at **Sree Sakthi Engineering College, Coimbatore**. I build software that solves real problems, with a growing focus on **LLM-powered apps, AI agents and automation**.

- 🤖 Goal: become an **AI Engineer / AI Agent Developer**
- 🧠 Exploring Machine Learning, Generative AI, RAG and tool-using agents
- 💻 Full-stack background: React, Node.js, Express, MongoDB
- 🛠️ Learn by shipping: every idea becomes a repo

## Tech Stack

<p>
  <img src="https://skillicons.dev/icons?i=python,js,html,css,react,nodejs,express,mongodb,git,github,linux" alt="Tech stack"/>
</p>

| Area | What I work on |
|---|---|
| **AI / ML** | Predictive models, LLM apps, prompting, RAG |
| **AI Agents** | Tool use, task execution, workflow automation |
| **Web** | Responsive frontends and REST backends |
| **Tools** | Git, GitHub, Linux, MongoDB |

## Featured Projects

| Project | Description | Stack |
|---|---|---|
| 🚆 [**ETA Railway System**](https://github.com/sabith-todo/ETA-Railway-System) | ML model that forecasts the Expected Time of Arrival of coaching trains | Python, ML |
| 🌱 [**IoT Smart Farming Monitor**](https://github.com/sabith-todo/IOT-Based-smart-farming-monitor) | Environmental monitoring, weather data and irrigation insights | IoT, Web |
| 🎓 [**Smart Campus Assistant**](https://github.com/sabith-todo/Smart-Campus-Assistants) | Lost-and-found management and live seat availability | Web |
| 📚 [**AI Study Planner**](https://github.com/sabith-todo/AI-Study-Planner) | Smart study planning to boost student productivity | AI, Web |
| 🛡️ [**SafeGuard AI**](https://github.com/sabith-todo/Safe_Guard-AI) | AI-driven safety solution | AI |
| 🧪 [**CRISIS-LAB**](https://github.com/sabith-todo/CRISIS-LAB) | Debugging arena built for an inter-college technical event | Web |

➡️ [See all repositories](https://github.com/sabith-todo?tab=repositories)

## GitHub Activity

<div align="center">

<a href="https://github.com/sabith-todo">
  <img src="https://streak-stats.demolab.com/?user=sabith-todo&theme=tokyonight&hide_border=true&border_radius=10&timezone=Asia%2FKolkata&date_format=M%20j%5B%2C%20Y%5D" alt="GitHub streak"/>
</a>

<br/><br/>

<img height="180" src="./profile-summary-card-output/tokyonight/3-stats.svg" alt="GitHub stats"/>
<img height="180" src="./profile-summary-card-output/tokyonight/2-most-commit-language.svg" alt="Most used languages"/>

<br/>

<img height="180" src="./profile-summary-card-output/tokyonight/1-repos-per-language.svg" alt="Repos per language"/>
<img height="180" src="./profile-summary-card-output/tokyonight/4-productive-time.svg" alt="Productive time"/>

<br/><br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/github-snake-dark.svg"/>
  <img alt="Contribution snake" src="./assets/github-snake.svg"/>
</picture>

</div>

## Roadmap

- **Now:** Python and problem-solving depth · core ML algorithms and evaluation
- **Next:** RAG pipelines · tool-using AI agents · AI features inside full-stack apps
- **Always:** real-world datasets · open-source contributions · documenting what I learn

## Let's Connect

Open to collaborating on AI, automation and web projects.

<div align="center">

<a href="https://github.com/sabith-todo"><img src="https://img.shields.io/badge/GitHub-Explore%20My%20Work-181717?style=for-the-badge&logo=github" alt="Explore my GitHub"/></a>

**Learn continuously. Build thoughtfully. Innovate with AI.** 🚀

</div>

name: Update Profile

on:
  schedule:
    - cron: "30 18 * * *"   # daily at 12:00 AM IST
  workflow_dispatch:         # manual run button
  push:
    branches: [main]

permissions:
  contents: write

jobs:
  update:
    runs-on: ubuntu-latest
    timeout-minutes: 15
    steps:
      - uses: actions/checkout@v4

      - name: Create assets folder
        run: mkdir -p assets

      - name: Generate contribution snake
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            assets/github-snake.svg
            assets/github-snake-dark.svg?palette=github-dark

      - name: Generate profile summary cards
        uses: vn7n24fzkq/github-profile-summary-cards@release/v4
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          USERNAME: ${{ github.repository_owner }}

      - name: Commit generated files
        uses: stefanzweifel/git-auto-commit-action@v5
        with:
          commit_message: "chore: update profile stats [skip ci]"
          file_pattern: "assets/*.svg profile-summary-card-output/**/*.svg"
