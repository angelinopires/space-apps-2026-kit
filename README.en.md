# Space Apps 2026 Kit

**Everything your team needs to build and ship a solution at the NASA Space Apps Challenge 2026, on November 14 and 15.**

This repository has the official hackathon information in one place and a set of AI skills to help with development. A skill is basically a file of instructions you hand to your AI assistant (Claude, ChatGPT, Cursor, Codex and the like). From then on it works the way the file says: picks the challenge with you, settles the visual design in minutes, builds fast and submits within the rules.

🇧🇷 [Versão em português](README.md)

> I have watched teams lose a hackathon weekend arguing about architecture. In 48 hours the winner is a project that runs, uses real NASA data and tells its story well. So the philosophy here is build fast, fail fast, fix fast. No automated tests, no pretty architecture, that comes after the event.

## What is here

| Folder | What it is |
| --- | --- |
| [`docs/en/challenges/`](docs/en/challenges/README.md) | The 14 official challenges. Each one has the background, what NASA expects, the points to watch and **the list of data and resources NASA itself recommends** |
| [`docs/en/rules-and-judging.md`](docs/en/rules-and-judging.md) | Dates, team rules, who can take part, what goes on the submission form, the 5 criteria judges use and the 10 global awards |
| [`docs/en/nasa-data-portals.md`](docs/en/nasa-data-portals.md) | Where to find NASA data for any challenge, and the traps that cost you hours |
| [`docs/pt-br/`](docs/pt-br/) | All of the above in Brazilian Portuguese |
| [`skills/`](skills/) | The AI skills, in the open [Agent Skills](https://agentskills.io) format |

## Install

Three ways, from the most automatic to the simplest. None needs a new account. If you are not a programmer, skip to way 3.

### 1. With a coding agent

A coding agent is an AI assistant that runs on your computer and edits your files: Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode. You need Node 22.20 or newer. Open a terminal inside the team's project folder and run:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

It asks which skills you want and for which tool. Accept all.

### 2. Manual, no Node

Download the repository and copy the `skills/` folder to where your tool reads skills, inside the team's project:

```bash
git clone https://github.com/angelinopires/space-apps-2026-kit.git
```

| Tool | Copy the contents of `skills/` into |
| --- | --- |
| Claude Code | `.claude/skills/` |
| Codex, Antigravity | `.agents/skills/` |
| Cursor | `.cursor/skills/` |
| Gemini CLI | `.gemini/skills/` |

Example for Claude Code:

```bash
mkdir -p .claude/skills && cp -r space-apps-2026-kit/skills/* .claude/skills/
```

### 3. Just the chat in your browser

ChatGPT, Gemini or Claude.ai, nothing to install. Open the `SKILL.md` file of the skill you want (they are in [`skills/`](skills/)), copy the whole text and paste it into the chat. Then paste the page of the challenge your team picked (it is in `docs/`). Done, the assistant knows what to do. The only difference is that it will not touch your files, you copy what it produces.

## How to use

Once installed, ask for the skill by name inside the tool:

| Tool | How to ask |
| --- | --- |
| Claude Code | `/choose-challenge`, or write "use the choose-challenge skill" |
| Codex, Cursor, Antigravity, Gemini CLI | Write "use the choose-challenge skill" |
| Browser chat | Paste the `SKILL.md`, then write what you need |

The assistant reads the skill, asks for what is missing and delivers what the skill promises.

## The weekend, step by step

**Saturday morning, before writing any code**

1. Read [`rules-and-judging.md`](docs/en/rules-and-judging.md). Five minutes, and it keeps the team from being disqualified over a 35-second video or a link that asks for a login.
2. Ask `/choose-challenge` and describe the team: how many people, what each one can do, how much time you have. It returns 2 or 3 challenges that fit you, each with a plan of what can be built in 24 hours.
3. Challenge chosen, ask `/hackathon-mode`. From then on the assistant works in hackathon mode: picks the technology for you, starts with sample data, puts the project online in the first 2 hours and does one thing at a time.
4. Before touching a color or a font, ask `/design-reference`. It takes a ready-made visual guide (palette, typography, components) that fits your challenge and applies it to the project. The team never argues about colors again.

**Saturday afternoon, once the screen works on sample data**

5. Ask `/nasa-data`. It swaps the sample for real NASA data without creating any account: four sources that answer right away (fires, weather, satellite imagery, NASA APIs), the exact URL for your region and dates, and the code to load it in your project. If the real source is not in by 7 PM, it tells you to keep the sample and say so in the submission, which judges prefer over a broken live fetch.

**Sunday afternoon**

6. Ask `/submit-and-demo`. It writes every field of the official submission form with the 5 judging criteria in mind, drafts the 30-second video script or the 7 slides, and checks item by item that everything is within the rules.
7. If your local event has a live presentation to the judges, ask `/pitch-deck`. It asks how many minutes the Local Lead gave you and whether there is Q&A, reads what you already wrote for the submission, and returns 6 slides with what is written and what the presenter says, timed, plus the 5 questions judges usually ask.

## The skills

| Skill | When | What you get |
| --- | --- | --- |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Saturday, first hour | 2 or 3 challenges that fit the team, each with the 24-hour plan, the NASA data to start from and the biggest risk |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | The whole build | The assistant in delivery mode: no tests, no login, no complications. Technology already chosen (website: Vite + React + Tailwind; data analysis: Python + Streamlit), project online before it is pretty, sample data before real data. At deploy time it explains each command in one sentence for someone who has never published anything, and has the list of what to do when it breaks |
| [`nasa-data`](skills/nasa-data/SKILL.md) | Saturday afternoon, when it is time for real data | The right source for what the screen needs, starting with the ones that need no login (FIRMS, POWER, GIBS, api.nasa.gov), the URL ready with region and dates, the loading code for React or Python, and when to stop and keep the sample |
| [`pitch-deck`](skills/pitch-deck/SKILL.md) | Before the live presentation at the local event | Your event's format (minutes, Q&A, slides) asked first, 6 slides with title, up to 3 bullets and each one's spoken line with the seconds, ready to paste into Google Slides, and the 5 judges' questions with an agreed answer |
| [`design-reference`](skills/design-reference/SKILL.md) | Before the first screen | A ready-made visual guide from the [awesome-design-md](https://github.com/VoltAgent/awesome-design-md) collection, chosen by challenge type and applied to the project. If the team prefers the look of a specific site, it extracts from there |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Sunday, last hours | The text for every submission field in English, the 30-second video script or the 7 slides, and the final checklist |

One I recommend but did not include, because it is Anthropic's and already ships as a plugin: the `frontend-design` skill, which produces interfaces well above what AI usually generates. In Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Questions

[Open an issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose). The answer stays public and becomes an FAQ for the other teams.

## To do

Still to do:

- Portuguese translation of the skills

## Sources and license

Challenge texts, rules and criteria come from the official [NASA Space Apps Challenge](https://www.spaceappschallenge.org/) website, reproduced and translated for offline reference. Where they differ, the official page is what counts. NASA does not endorse this repository.

The `DESIGN.md` files the `design-reference` skill uses come from [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (MIT license).

This repository's own code and text: [MIT license](LICENSE).

---

Created by [Angelino Pires](https://instagram.com/tech_lino).
