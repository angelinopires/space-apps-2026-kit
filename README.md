# Space Apps 2026 Kit

**Tudo que o seu time precisa pra construir e lançar uma solução no NASA Space Apps Challenge 2026, nos dias 14 e 15 de novembro.**

Aqui tem a informação oficial do hackathon em português e um conjunto de skills de IA pra ajudar no desenvolvimento. Skill, que basicamente é um arquivo de instruções que você dá pro seu assistente de IA (Claude, ChatGPT, Cursor, Codex e afins), e a partir dali ele passa a trabalhar do jeito que o arquivo manda: escolher o desafio com você, fechar o visual em minutos, construir rápido e submeter dentro das regras.

🇺🇸 [English version](README.en.md)

> Eu já vi time perder o fim de semana de hackathon discutindo arquitetura. Em 48 horas o que vence é um projeto que roda, usa dado da NASA de verdade e conta bem a história. Então a filosofia aqui é: fazer rápido, errar rápido, corrigir rápido. Nada de teste automatizado, nada de arquitetura bonita, isso fica pra depois do evento.

## O que tem aqui

| Pasta | O que é |
| --- | --- |
| [`docs/pt-br/desafios/`](docs/pt-br/desafios/README.md) | Os 14 desafios oficiais traduzidos. Cada um tem o contexto, o que a NASA espera, os pontos de atenção e **a lista de dados e recursos que a própria NASA recomenda** |
| [`docs/pt-br/regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md) | Datas, regras de time, quem pode participar, o que vai no formulário de submissão, os 5 critérios que os jurados usam e os 10 prêmios globais |
| [`docs/pt-br/portais-de-dados-nasa.md`](docs/pt-br/portais-de-dados-nasa.md) | Onde achar dado da NASA pra qualquer desafio, e as armadilhas que fazem você perder horas |
| [`docs/en/`](docs/en/) | Tudo acima em inglês |
| [`skills/`](skills/) | As skills de IA, no padrão aberto [Agent Skills](https://agentskills.io). Estão em inglês porque é o idioma que os assistentes entendem melhor, mas você conversa com eles em português normal |

## Instalação

Tem três jeitos, do mais automático ao mais simples. Nenhum pede conta nova. Se você não é da área de programação, pula direto pro jeito 3.

### 1. Com um agente de código

Agente de código é um assistente de IA que roda no seu computador e mexe nos seus arquivos: Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode. Precisa do Node 22.20 ou mais novo instalado. Abra o terminal dentro da pasta do projeto do time e rode:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

Ele pergunta quais skills você quer e pra qual ferramenta. Aceita todas.

### 2. Manual, sem Node

Baixe o repositório e copie a pasta `skills/` pra onde a sua ferramenta lê skills, dentro do projeto do time:

```bash
git clone https://github.com/angelinopires/space-apps-2026-kit.git
```

| Ferramenta | Copiar o conteúdo de `skills/` para |
| --- | --- |
| Claude Code | `.claude/skills/` |
| Codex, Antigravity | `.agents/skills/` |
| Cursor | `.cursor/skills/` |
| Gemini CLI | `.gemini/skills/` |

Exemplo pro Claude Code:

```bash
mkdir -p .claude/skills && cp -r space-apps-2026-kit/skills/* .claude/skills/
```

### 3. Só com o chat no navegador

ChatGPT, Gemini ou Claude.ai, sem instalar nada. Abra o arquivo `SKILL.md` da skill que você quer (estão em [`skills/`](skills/)), copie o texto inteiro e cole no chat. Depois cole também a página do desafio que o time escolheu (está em `docs/`). Pronto, o assistente já sabe o que fazer. A única diferença é que ele não vai mexer nos seus arquivos, você copia o que ele gerar.

## Como usar

Depois de instalar, é só pedir pelo nome dentro da ferramenta:

| Ferramenta | Como pedir |
| --- | --- |
| Claude Code | `/choose-challenge`, ou escreva "use a skill choose-challenge" |
| Codex, Cursor, Antigravity, Gemini CLI | Escreva "use a skill choose-challenge" |
| Chat no navegador | Cole o `SKILL.md` e depois escreva o que você precisa |

O assistente lê a skill, pergunta o que falta e entrega o que ela promete. Pode falar em português.

## O fim de semana, passo a passo

**Sábado de manhã, antes de escrever qualquer código**

1. Leia [`regras-e-julgamento.md`](docs/pt-br/regras-e-julgamento.md). São 5 minutos, e evita o time ser desclassificado por um vídeo de 35 segundos ou um link que pede login.
2. Peça `/choose-challenge` e descreva o time: quantas pessoas, o que cada uma sabe fazer, quanto tempo vocês têm. Ele devolve 2 ou 3 desafios que combinam com vocês, cada um com um plano do que dá pra construir em 24 horas.
3. Escolhido o desafio, peça `/hackathon-mode`. A partir daí o assistente trabalha no modo hackathon: escolhe a tecnologia por você, começa com dados de exemplo, coloca o projeto no ar nas primeiras 2 horas e faz uma coisa de cada vez.
4. Antes de mexer em cor ou fonte, peça `/design-reference`. Ele pega um guia visual pronto (paleta, tipografia, componentes) que combina com o seu desafio e aplica no projeto. O time não discute cor nunca mais.

**Sábado à tarde, quando a tela já funciona com dado de exemplo**

5. Peça `/nasa-data`. Ele troca o dado de exemplo por dado real da NASA sem criar conta nenhuma: quatro fontes que respondem na hora (queimadas, clima, imagem de satélite, APIs da NASA), a URL exata pra sua região e data, e o código pra carregar no seu projeto. Se a fonte real não entrar até as 19h, ele te manda ficar com a amostra e escrever isso na submissão, que é o que os jurados preferem a um fetch quebrado.

**Domingo à tarde**

6. Peça `/submit-and-demo`. Ele escreve, em inglês, cada campo do formulário oficial de submissão pensando nos 5 critérios dos jurados, monta o roteiro do vídeo de 30 segundos ou dos 7 slides, e confere item por item se está tudo dentro das regras.
7. Se o seu evento local tem apresentação ao vivo pros jurados, peça `/pitch-deck`. Ele pergunta quantos minutos o Local Lead deu e se tem perguntas depois, lê o que você já escreveu na submissão e devolve 6 slides com o que vai escrito e o que o apresentador fala, cronometrado, mais as 5 perguntas que os jurados costumam fazer.

## As skills

| Skill | Quando usar | O que você recebe |
| --- | --- | --- |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Sábado, primeira hora | 2 ou 3 desafios que combinam com o time, cada um com o plano de 24 horas, o dado da NASA pra começar e o maior risco |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | O build inteiro | O assistente no modo "entrega": sem teste, sem login, sem complicação. Tecnologia já escolhida (site: Vite + React + Tailwind; análise de dados: Python + Streamlit), projeto no ar antes de ficar bonito, dado de exemplo antes do dado real. Na hora do deploy, explica cada comando em uma frase pra quem nunca publicou nada e tem a lista do que fazer quando quebra |
| [`nasa-data`](skills/nasa-data/SKILL.md) | Sábado à tarde, na hora de ligar o dado real | A fonte certa pro que a tela precisa, começando pelas que não pedem login (FIRMS, POWER, GIBS, api.nasa.gov), a URL pronta com região e data, o código pra carregar em React ou Python, e a hora de parar e ficar com a amostra |
| [`pitch-deck`](skills/pitch-deck/SKILL.md) | Antes da apresentação ao vivo no evento local | O formato do seu evento (minutos, perguntas, slides) perguntado primeiro, 6 slides com título, até 3 bullets e a fala de cada um com os segundos, pra colar no Google Slides, e as 5 perguntas dos jurados com resposta combinada |
| [`design-reference`](skills/design-reference/SKILL.md) | Antes da primeira tela | Um guia visual pronto do acervo [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), escolhido pelo tipo do desafio e aplicado no projeto. Se o time prefere o visual de um site específico, ele extrai de lá |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Domingo, últimas horas | O texto de cada campo da submissão em inglês, o roteiro do vídeo de 30 segundos ou dos 7 slides, e a lista de conferência final |

Uma que eu recomendo mas não está aqui, porque é da Anthropic e já existe como plugin: a skill `frontend-design`, que faz interface com acabamento bem acima do padrão que a IA costuma gerar. No Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Dúvidas

[Abra uma issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose). A resposta fica pública e vira FAQ pros outros times.

## A fazer

O que ficou de fora:

- Tradução das skills pra português

## Fontes e licença

Os textos dos desafios, regras e critérios vêm do site oficial do [NASA Space Apps Challenge](https://www.spaceappschallenge.org/), reproduzidos e traduzidos pra consulta offline. Se algo divergir, a página oficial é que vale. A NASA não endossa este repositório.

Os arquivos `DESIGN.md` que a skill `design-reference` usa vêm do [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (licença MIT).

Código e textos próprios deste repositório: [licença MIT](LICENSE).

---

Criado por [Angelino Pires](https://instagram.com/tech_lino).
