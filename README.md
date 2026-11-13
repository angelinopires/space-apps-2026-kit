# Space Apps 2026 Kit

**Mentor remoto em forma de repositório para o NASA Space Apps Challenge 2026 (14 e 15 de novembro).**
Toda a informação oficial do hackathon em português, mais quatro skills de IA para o seu agente de código (Claude Code, Codex, Cursor, Antigravity ou qualquer chat) ajudar o time a escolher desafio, resolver design em minutos, construir rápido e submeter certo.

🇺🇸 [English version](README.en.md)

> Filosofia: fazer rápido, errar rápido, corrigir rápido. Nada de TDD, nada de arquitetura. Em 48 horas o que vence é um projeto que roda, usa dado da NASA de verdade e conta bem a história.

## O que tem aqui

| Pasta | Conteúdo |
| --- | --- |
| [`docs/pt-br/desafios/`](docs/pt-br/desafios/README.md) | Os 14 desafios oficiais traduzidos, cada um com contexto, objetivos, pontos a considerar e **a lista de datasets e recursos recomendados pela NASA** |
| [`docs/pt-br/regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md) | Datas, regras de time, requisitos de elegibilidade, campos do formulário de submissão, os 5 critérios de julgamento e os 10 prêmios globais |
| [`docs/pt-br/portais-de-dados-nasa.md`](docs/pt-br/portais-de-dados-nasa.md) | Portais de dados da NASA que servem para qualquer desafio e as armadilhas que custam horas |
| [`docs/en/`](docs/en/) | Tudo acima em inglês |
| [`skills/`](skills/) | Quatro skills no padrão aberto Agent Skills (`SKILL.md`), em inglês |

## Instalação

Escolha o caminho que combina com a sua ferramenta. Nenhum deles precisa de conta nova.

**1. Qualquer agente que suporte Agent Skills** (Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode e outros). Exige Node 22.20 ou mais novo:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

**2. Manual** (funciona sem Node). Clone e copie a pasta `skills/` para onde a sua ferramenta lê skills, dentro do projeto do time:

```bash
git clone https://github.com/angelinopires/space-apps-2026-kit.git
```

| Ferramenta | Copiar `skills/*` para |
| --- | --- |
| Claude Code | `.claude/skills/` |
| Codex, Antigravity | `.agents/skills/` |
| Cursor | `.cursor/skills/` |
| Gemini CLI | `.gemini/skills/` |

**3. Sem agente de código** (ChatGPT, Gemini, Claude.ai no navegador). Abra o `SKILL.md` da skill que quiser, cole o conteúdo no chat e depois cole a página do desafio escolhido. Funciona igual.

## Como usar no fim de semana

Sábado de manhã, antes de escrever código:

1. Leia [`regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md). Leva 5 minutos e evita a desclassificação por demo longa demais ou link privado.
2. Peça ao agente: **"use a skill choose-challenge"** e descreva o time (quantas pessoas, o que cada uma sabe, quanto tempo têm). Ele cruza isso com os 14 desafios e devolve 2 ou 3 candidatos com um MVP de 24 horas para cada.
3. Escolhido o desafio, peça: **"use a skill hackathon-mode"**. A partir daí o agente trabalha no modo hackathon: stack opinativa, dados mockados primeiro, deploy nas primeiras 2 horas, uma feature por vez.
4. Antes de abrir o editor de CSS: **"use a skill design-reference"**. O agente escolhe um `DESIGN.md` pronto (paleta, tipografia, componentes) da família do seu desafio e o time nunca mais discute cor.

Domingo à tarde:

5. **"use a skill submit-and-demo"**. O agente escreve, em inglês, cada campo da página oficial de submissão alinhado aos 5 critérios, gera o roteiro da demo de 30 segundos ou dos 7 slides e roda o checklist de link público.

## As skills

| Skill | O que faz |
| --- | --- |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | Postura do agente para 48 horas: sem testes, sem auth, sem abstração. Stack em duas trilhas (web: Vite + React + Tailwind; dados: Python + Streamlit), deploy antes de polir, mock antes de API real |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Cruza as habilidades e o tamanho do time com os 14 desafios e os critérios de julgamento; devolve candidatos com MVP de 24 h e os datasets do próprio desafio |
| [`design-reference`](skills/design-reference/SKILL.md) | Resolve o design em minutos com um `DESIGN.md` pronto do acervo [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), mapeado por tipo de desafio; fallback para extrair de um site que o time escolher |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Escreve os campos da página de submissão em inglês, pontuando cada critério, e o roteiro da demo dentro dos limites oficiais (30 s ou 7 slides) |

Recomendada, mas não incluída (é da Anthropic e já existe como plugin): a skill `frontend-design`, que produz interfaces com acabamento acima do padrão de IA. No Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Mentoria

Este repositório é a mentoria. Eu, Lino, sou mentor do evento mas não estarei disponível durante o fim de semana. Dúvidas que ficarem respondo depois:

- Instagram: [@tech_lino](https://instagram.com/tech_lino)
- LinkedIn: [angelinopires](https://linkedin.com/in/angelinopires)
- [Abra uma issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose) neste repositório. Vira FAQ para os outros times.

## A fazer

Ideias de skills que ficaram de fora da primeira versão. Se o kit for útil, elas entram:

- `ship-fast`: deploy em um comando (Vercel, Netlify, GitHub Pages, Streamlit Cloud, Hugging Face Spaces)
- `nasa-data`: como achar, recortar e baixar dados NASA rápido (Earthdata, GIBS, AppEEARS, formatos HDF/NetCDF)
- `pitch-deck`: slides da apresentação local (5 minutos) a partir do README do projeto
- Tradução das skills para português

## Fontes e licença

Os textos dos desafios, regras e critérios são do site oficial do [NASA Space Apps Challenge](https://www.spaceappschallenge.org/), reproduzidos e traduzidos para consulta offline. Em caso de divergência, a página oficial prevalece. NASA não endossa este repositório.

Os arquivos `DESIGN.md` referenciados pela skill `design-reference` vêm do [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (licença MIT).

Código e textos próprios deste repositório: [licença MIT](LICENSE).
