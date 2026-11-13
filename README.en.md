# Space Apps 2026 Kit

**A remote mentor in the shape of a repository for the NASA Space Apps Challenge 2026 (November 14-15).**
All the official hackathon information in one place, plus four AI skills so your coding agent (Claude Code, Codex, Cursor, Antigravity or any chat) helps the team pick a challenge, settle design in minutes, build fast and submit right.

🇧🇷 [Versão em português](README.md)

> Philosophy: build fast, fail fast, fix fast. No TDD, no architecture. In 48 hours the winner is a project that runs, uses real NASA data and tells its story well.

## What is here

| Folder | Contents |
| --- | --- |
| [`docs/en/challenges/`](docs/en/challenges/README.md) | The 14 official challenges, each with background, objectives, considerations and **the datasets and resources NASA recommends** |
| [`docs/en/rules-and-judging.md`](docs/en/rules-and-judging.md) | Dates, team rules, eligibility, submission form fields, the 5 judging criteria and the 10 global awards |
| [`docs/en/nasa-data-portals.md`](docs/en/nasa-data-portals.md) | NASA data portals that work for any challenge, and the traps that cost hours |
| [`docs/pt-br/`](docs/pt-br/) | Everything above in Brazilian Portuguese |
| [`skills/`](skills/) | Four skills in the open Agent Skills format (`SKILL.md`) |

## Install

Pick the path that matches your tool. None needs a new account.

**1. Any agent that supports Agent Skills** (Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode and others). Needs Node 22.20 or newer:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

**2. Manual** (no Node needed). Clone and copy the `skills/` folder to where your tool reads skills, inside the team's project:

```bash
git clone https://github.com/angelinopires/space-apps-2026-kit.git
```

| Tool | Copy `skills/*` into |
| --- | --- |
| Claude Code | `.claude/skills/` |
| Codex, Antigravity | `.agents/skills/` |
| Cursor | `.cursor/skills/` |
| Gemini CLI | `.gemini/skills/` |

**3. No coding agent** (ChatGPT, Gemini, Claude.ai in the browser). Open the `SKILL.md` you want, paste its content into the chat, then paste the page of your chosen challenge. Works the same.

## How to use it over the weekend

Saturday morning, before writing code:

1. Read [`rules-and-judging.md`](docs/en/rules-and-judging.md). Five minutes, and it prevents disqualification for a demo that runs long or a private link.
2. Ask the agent: **"use the choose-challenge skill"** and describe the team (how many people, what each knows, how much time you have). It matches that against the 14 challenges and returns 2 or 3 candidates with a 24-hour MVP for each.
3. Challenge chosen, ask: **"use the hackathon-mode skill"**. From then on the agent works in hackathon mode: opinionated stack, mock data first, deploy in the first 2 hours, one feature at a time.
4. Before opening the CSS editor: **"use the design-reference skill"**. The agent picks a ready-made `DESIGN.md` (palette, typography, components) for your challenge family and the team never argues about colors again.

Sunday afternoon:

5. **"use the submit-and-demo skill"**. The agent writes every field of the official submission page against the 5 criteria, produces the 30-second video script or the 7-slide outline, and runs the public-link checklist.

## The skills

| Skill | What it does |
| --- | --- |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | The agent's posture for 48 hours: no tests, no auth, no abstractions. Two-lane stack (web: Vite + React + Tailwind; data: Python + Streamlit), deploy before polish, mock before live API |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Matches team skills and size against the 14 challenges and the judging criteria; returns candidates with a 24-hour MVP and the challenge's own datasets |
| [`design-reference`](skills/design-reference/SKILL.md) | Settles design in minutes with a ready-made `DESIGN.md` from [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), mapped by challenge type; falls back to extracting from a site the team picks |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Writes the submission page fields in English, scoring each criterion, plus the demo script within the official limits (30 s or 7 slides) |

Recommended but not bundled (it is Anthropic's and already ships as a plugin): the `frontend-design` skill, which produces interfaces well above the usual AI look. In Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Mentoring

This repository is the mentoring. I, Lino, am a mentor at the event but will not be available during the weekend. Questions left open get answered afterwards:

- Instagram: [@tech_lino](https://instagram.com/tech_lino)
- LinkedIn: [angelinopires](https://linkedin.com/in/angelinopires)
- [Open an issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose) here. It becomes an FAQ for the other teams.

## To do

Skill ideas left out of the first version. If the kit proves useful, they come next:

- `ship-fast`: one-command deploy (Vercel, Netlify, GitHub Pages, Streamlit Cloud, Hugging Face Spaces)
- `nasa-data`: how to find, subset and download NASA data fast (Earthdata, GIBS, AppEEARS, HDF/NetCDF formats)
- `pitch-deck`: slides for the local 5-minute presentation from the project README
- Portuguese translation of the skills

## Sources and license

Challenge texts, rules and criteria come from the official [NASA Space Apps Challenge](https://www.spaceappschallenge.org/) website, reproduced and translated for offline reference. Where they differ, the official page prevails. NASA does not endorse this repository.

The `DESIGN.md` files referenced by the `design-reference` skill come from [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (MIT license).

This repository's own code and text: [MIT license](LICENSE).
