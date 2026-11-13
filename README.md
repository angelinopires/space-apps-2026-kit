# Space Apps 2026 Kit

**Tudo que um time precisa para construir e lançar uma solução no NASA Space Apps Challenge 2026 (14 e 15 de novembro).**
Informação oficial do hackathon em português, mais skills de IA que ajudam no desenvolvimento durante o hackathon: o seu agente de código (Claude Code, Codex, Cursor, Antigravity, Gemini CLI ou qualquer chat) escolher desafio, fechar o design em minutos, construir rápido e submeter dentro das regras.

🇺🇸 [English version](README.en.md)

> Filosofia: fazer rápido, errar rápido, corrigir rápido. Nada de TDD, nada de arquitetura. Em 48 horas o que vence é um projeto que roda, usa dado da NASA de verdade e conta bem a história.

## O que tem aqui

| Pasta | Conteúdo |
| --- | --- |
| [`docs/pt-br/desafios/`](docs/pt-br/desafios/README.md) | Os 14 desafios oficiais traduzidos, cada um com contexto, objetivos, pontos a considerar e **a lista de datasets e recursos recomendados pela NASA** |
| [`docs/pt-br/regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md) | Datas, regras de time, requisitos de elegibilidade, campos do formulário de submissão, os 5 critérios de julgamento e os 10 prêmios globais |
| [`docs/pt-br/portais-de-dados-nasa.md`](docs/pt-br/portais-de-dados-nasa.md) | Portais de dados da NASA que servem para qualquer desafio e as armadilhas que custam horas |
| [`docs/en/`](docs/en/) | Tudo acima em inglês |
| [`skills/`](skills/) | Skills de IA para o desenvolvimento no hackathon, no padrão aberto [Agent Skills](https://agentskills.io) (`SKILL.md`), em inglês |

## Instalação

Escolha o caminho da sua ferramenta. Nenhum precisa de conta nova.

### 1. Agente que suporta Agent Skills (recomendado)

Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode e outros. Exige Node 22.20 ou mais novo. Rode dentro da pasta do projeto do time:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

O instalador pergunta quais skills e para qual ferramenta. Aceite todas.

### 2. Manual (sem Node)

Clone e copie a pasta `skills/` para onde a sua ferramenta lê skills, dentro do projeto do time:

```bash
git clone https://github.com/angelinopires/space-apps-2026-kit.git
```

| Ferramenta | Copiar o conteúdo de `skills/` para |
| --- | --- |
| Claude Code | `.claude/skills/` |
| Codex, Antigravity | `.agents/skills/` |
| Cursor | `.cursor/skills/` |
| Gemini CLI | `.gemini/skills/` |

Exemplo para Claude Code:

```bash
mkdir -p .claude/skills && cp -r space-apps-2026-kit/skills/* .claude/skills/
```

### 3. Sem agente de código

ChatGPT, Gemini, Claude.ai no navegador. Abra o `SKILL.md` da skill que quiser, cole o conteúdo inteiro no chat e, em seguida, cole a página do desafio escolhido (de `docs/`). Funciona igual, só sem acesso aos seus arquivos.

## Como rodar

Depois de instalar, basta pedir pelo nome dentro do agente. Exemplos:

| Ferramenta | Como invocar |
| --- | --- |
| Claude Code | `/choose-challenge` ou "use a skill choose-challenge" |
| Codex, Cursor, Antigravity, Gemini CLI | "use a skill choose-challenge" no prompt |
| Chat no navegador | Cole o `SKILL.md` e depois escreva o pedido |

O agente lê a skill e já sabe o que perguntar e o que entregar. Você pode falar em português; a skill está em inglês mas o agente responde no seu idioma.

## Fluxo sugerido para o fim de semana

**Sábado de manhã, antes de escrever código**

1. Leia [`regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md). Leva 5 minutos e evita desclassificação por demo longa demais ou link privado.
2. `/choose-challenge` e descreva o time (quantas pessoas, o que cada uma sabe, quanto tempo têm). Volta com 2 ou 3 desafios candidatos e um MVP de 24 horas para cada.
3. Desafio escolhido: `/hackathon-mode`. A partir daí o agente trabalha no modo hackathon: stack opinativa, dados mockados primeiro, deploy nas primeiras 2 horas, uma feature por vez.
4. Antes de mexer em CSS: `/design-reference`. O agente escolhe um `DESIGN.md` pronto (paleta, tipografia, componentes) para a família do seu desafio e o time não discute cor nunca mais.

**Domingo à tarde**

5. `/submit-and-demo`. O agente escreve cada campo da página oficial de submissão em inglês, alinhado aos 5 critérios, gera o roteiro do vídeo de 30 segundos ou dos 7 slides e roda o checklist de link público.

## As skills

| Skill | Quando usar | O que entrega |
| --- | --- | --- |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Sábado, primeira hora | 2 ou 3 desafios candidatos cruzados com o time, cada um com MVP de 24 h, dataset inicial e risco principal |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | Durante todo o build | Postura de 48 horas: sem testes, sem auth, sem abstração. Stack em duas trilhas (web: Vite + React + Tailwind; dados: Python + Streamlit), deploy antes de polir, mock antes de API real |
| [`design-reference`](skills/design-reference/SKILL.md) | Antes da primeira tela | Um `DESIGN.md` pronto do acervo [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), escolhido pelo tipo de desafio, aplicado ao projeto. Fallback: extrair de um site que o time indicar |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Domingo, últimas horas | Texto de cada campo da submissão em inglês, roteiro do vídeo de 30 s ou dos 7 slides, checklist de elegibilidade |

Recomendada, não incluída (é da Anthropic e já existe como plugin): a skill `frontend-design`, que produz interfaces com acabamento acima do padrão de IA. No Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Dúvidas

[Abra uma issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose). Vira FAQ para os outros times.

## A fazer

Skills que ficaram de fora da primeira versão:

- `ship-fast`: deploy em um comando (Vercel, Netlify, GitHub Pages, Streamlit Cloud, Hugging Face Spaces)
- `nasa-data`: como achar, recortar e baixar dados NASA rápido (Earthdata, GIBS, AppEEARS, formatos HDF/NetCDF)
- `pitch-deck`: slides da apresentação local (5 minutos) a partir do README do projeto
- Tradução das skills para português

## Fontes e licença

Os textos dos desafios, regras e critérios são do site oficial do [NASA Space Apps Challenge](https://www.spaceappschallenge.org/), reproduzidos e traduzidos para consulta offline. Em caso de divergência, a página oficial prevalece. NASA não endossa este repositório.

Os arquivos `DESIGN.md` referenciados pela skill `design-reference` vêm do [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (licença MIT).

Código e textos próprios deste repositório: [licença MIT](LICENSE).

---

Criado por [Angelino Pires](https://instagram.com/tech_lino).
