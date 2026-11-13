# Space Apps 2026 Kit

**Everything a team needs to build and ship a solution at the NASA Space Apps Challenge 2026 (November 14-15).**
All the official hackathon information in one place, plus AI skills that help with development during the hackathon: your coding agent (Claude Code, Codex, Cursor, Antigravity, Gemini CLI or any chat) pick a challenge, settle design in minutes, build fast and submit within the rules.

🇧🇷 [Versão em português](README.md)

> Philosophy: build fast, fail fast, fix fast. No TDD, no architecture. In 48 hours the winner is a project that runs, uses real NASA data and tells its story well.

## What is here

| Folder | Contents |
| --- | --- |
| [`docs/en/challenges/`](docs/en/challenges/README.md) | The 14 official challenges, each with background, objectives, considerations and **the datasets and resources NASA recommends** |
| [`docs/en/rules-and-judging.md`](docs/en/rules-and-judging.md) | Dates, team rules, eligibility, submission form fields, the 5 judging criteria and the 10 global awards |
| [`docs/en/nasa-data-portals.md`](docs/en/nasa-data-portals.md) | NASA data portals that work for any challenge, and the traps that cost hours |
| [`docs/pt-br/`](docs/pt-br/) | Everything above in Brazilian Portuguese |
| [`skills/`](skills/) | AI skills for hackathon development, in the open [Agent Skills](https://agentskills.io) format (`SKILL.md`) |

## Install

Pick the path for your tool. None needs a new account.

### 1. Agent that supports Agent Skills (recommended)

Claude Code, Codex, Cursor, Antigravity, Gemini CLI, OpenCode and others. Needs Node 22.20 or newer. Run inside the team's project folder:

```bash
npx skills add angelinopires/space-apps-2026-kit
```

The installer asks which skills and which tool. Accept all.

### 2. Manual (no Node)

Clone and copy the `skills/` folder to where your tool reads skills, inside the team's project:

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

### 3. No coding agent

ChatGPT, Gemini, Claude.ai in the browser. Open the `SKILL.md` you want, paste its whole content into the chat, then paste the page of your chosen challenge (from `docs/`). Works the same, just without access to your files.

## Run

Once installed, ask for the skill by name inside the agent. Examples:

| Tool | How to invoke |
| --- | --- |
| Claude Code | `/choose-challenge` or "use the choose-challenge skill" |
| Codex, Cursor, Antigravity, Gemini CLI | "use the choose-challenge skill" in the prompt |
| Browser chat | Paste the `SKILL.md`, then write your request |

The agent reads the skill and knows what to ask and what to deliver.

## Suggested flow for the weekend

**Saturday morning, before writing code**

1. Read [`rules-and-judging.md`](docs/en/rules-and-judging.md). Five minutes, and it prevents disqualification for a demo that runs long or a private link.
2. `/choose-challenge` and describe the team (how many people, what each knows, how much time you have). Returns 2 or 3 candidate challenges with a 24-hour MVP for each.
3. Challenge chosen: `/hackathon-mode`. From then on the agent works in hackathon mode: opinionated stack, mock data first, deploy in the first 2 hours, one feature at a time.
4. Before touching CSS: `/design-reference`. The agent picks a ready-made `DESIGN.md` (palette, typography, components) for your challenge family and the team never argues about colors again.

**Sunday afternoon**

5. `/submit-and-demo`. The agent writes every field of the official submission page in English against the 5 criteria, produces the 30-second video script or the 7-slide outline, and runs the public-link checklist.

## The skills

| Skill | When | What you get |
| --- | --- | --- |
| [`choose-challenge`](skills/choose-challenge/SKILL.md) | Saturday, first hour | 2 or 3 candidate challenges matched to the team, each with a 24 h MVP, starting dataset and main risk |
| [`hackathon-mode`](skills/hackathon-mode/SKILL.md) | The whole build | 48-hour posture: no tests, no auth, no abstractions. Two-lane stack (web: Vite + React + Tailwind; data: Python + Streamlit), deploy before polish, mock before live API |
| [`design-reference`](skills/design-reference/SKILL.md) | Before the first screen | A ready-made `DESIGN.md` from [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), chosen by challenge type, applied to the project. Fallback: extract from a site the team names |
| [`submit-and-demo`](skills/submit-and-demo/SKILL.md) | Sunday, last hours | Text for every submission field in English, 30 s video script or 7-slide outline, eligibility checklist |

Recommended but not bundled (it is Anthropic's and already ships as a plugin): the `frontend-design` skill, which produces interfaces well above the usual AI look. In Claude Code: `/plugin install frontend-design@claude-plugins-official`.

## Questions

[Open an issue](https://github.com/angelinopires/space-apps-2026-kit/issues/new/choose). It becomes an FAQ for the other teams.

## To do

Skills left out of the first version:

- `ship-fast`: one-command deploy (Vercel, Netlify, GitHub Pages, Streamlit Cloud, Hugging Face Spaces)
- `nasa-data`: how to find, subset and download NASA data fast (Earthdata, GIBS, AppEEARS, HDF/NetCDF formats)
- `pitch-deck`: slides for the local 5-minute presentation from the project README
- Portuguese translation of the skills

## Sources and license

Challenge texts, rules and criteria come from the official [NASA Space Apps Challenge](https://www.spaceappschallenge.org/) website, reproduced and translated for offline reference. Where they differ, the official page prevails. NASA does not endorse this repository.

The `DESIGN.md` files referenced by the `design-reference` skill come from [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md) (MIT license).

This repository's own code and text: [MIT license](LICENSE).

---

Created by [Angelino Pires](https://instagram.com/tech_lino).
