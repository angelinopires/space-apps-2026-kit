---
name: design-reference
description: Settles the visual design of a hackathon project in minutes by picking a ready-made DESIGN.md (palette, typography, spacing, components) from the awesome-design-md collection, mapped to the type of NASA Space Apps challenge, and applying it to the codebase. Use before building the first screen, when the user says "design", "colors", "make it look good", "ugly", or wants to copy the look of a specific site. Includes a fallback for extracting a DESIGN.md from any URL the team names.
---

# Design Reference

A hackathon team should spend zero minutes arguing about colors. This skill picks a complete design system from a curated collection, writes it into the project, and derives the Tailwind or CSS tokens from it. The agent then follows that file for every screen.

## Step 1: pick the family

Match the chosen challenge (or the project's mood) to one row. If the user names a brand they like, skip to Step 2 with that name if it exists in the list.

| Family | Fits challenges | DESIGN.md candidates (pick the first unless the user prefers another) |
| --- | --- | --- |
| Dark data, space, mission control | 02, 04, 06, 09, 10, 11, 12 | `spacex`, `nvidia` |
| Analytics dashboard, monitoring | 02, 05, 07, 09 | `sentry`, `posthog` |
| Editorial, storytelling, archive | 01, 14 | `theverge`, `wired`, `notion` |
| Game, playful, retro | 03, 13 | `nintendo-2001`, `playstation` |
| Kids, colorful, friendly | 03, 08 | `airtable`, `figma` |
| Clean utility, forms, tools | 05, 07, 13 | `linear.app`, `vercel`, `cal` |
| Science, AI, calm | 08, 12 | `claude`, `cohere` |

If a challenge appears in several rows, take the row closest to the app's main screen: map and chart apps go to "Analytics dashboard", story and gallery apps to "Editorial". Marketing-site systems such as `spacex` have no chart or accent tokens; when the file lacks one, derive the accent from the data palette (see Step 3).

All files live in `https://github.com/VoltAgent/awesome-design-md` under `design-md/<name>/DESIGN.md` (MIT license). Browse that folder for other names if none fits.

## Step 2: fetch it into the project

```bash
NAME=spacex   # change
curl -fsSL "https://raw.githubusercontent.com/VoltAgent/awesome-design-md/main/design-md/$NAME/DESIGN.md" -o DESIGN.md
```

If `curl` fails (offline, wrong name), open `https://github.com/VoltAgent/awesome-design-md/tree/main/design-md` in the browser, find the folder, copy the raw content into `DESIGN.md` by hand.

Add one line to `SOURCES.md`: `Design system adapted from VoltAgent/awesome-design-md (<name>/DESIGN.md), MIT license.` It belongs in the submission's References field.

## Step 3: apply it

Read `DESIGN.md` fully. Then:

1. **Tokens.** Extract the colors, font families, radii and spacing into the project's single source of truth:
   - Tailwind v4: `@theme { --color-bg: ...; --color-fg: ...; --color-accent: ...; --font-sans: ...; --radius-md: ...; }` inside `src/index.css`, right after `@import "tailwindcss";`.
   - Plain CSS or Streamlit: `:root { --bg: ...; }` in the main stylesheet. In Streamlit, put the same values in `.streamlit/config.toml` under `[theme]` (`primaryColor`, `backgroundColor`, `secondaryBackgroundColor`, `textColor`, `font`).
2. **Fonts.** If the DESIGN.md names a paid or proprietary font, substitute the closest Google Font (geometric sans such as D-DIN or Helvetica: Inter or Space Grotesk; humanist: Source Sans 3; mono: IBM Plex Mono; serif: Source Serif 4) and note it in `DESIGN.md`. Load it with one `<link>` tag in `index.html`.
3. **Three components first:** page shell (background, max width, padding), one card, one button. Everything else is a variation of these three. Do not build a component library.
4. **One accent color.** Whatever the DESIGN.md offers (or does not: many brand files have none), the app uses one accent for interactive elements and status, plus neutrals. Two accents at most if the data needs a diverging scale.
5. **Data colors.** For charts and maps, use a sequential or diverging palette that reads on the chosen background (for dark themes, start from the accent and lighten). Never rainbow.
6. Keep `DESIGN.md` in the repo root and re-read it before each new screen. When the user asks for "something different", edit `DESIGN.md` first, then the code.

## Rules that do not bend

- **No NASA logos, insignia or Space Apps branding** inside the app. Use the phrase "Built with NASA data" in plain text. Mission names and public-domain NASA images are fine; cite them in `SOURCES.md`.
- **Contrast**: body text at least 4.5:1 against its background, large headings 3:1. If the DESIGN.md's palette fails this on your background, darken or lighten the text token; do not keep an unreadable brand color for fidelity.
- **Touch targets** of at least 44 px for anything clickable; judges open demos on phones. Marketing-site button sizes in a DESIGN.md do not override this.
- Design is done when the three components exist and the first screen uses them. Stop polishing and go back to the `hackathon-mode` checkpoints.

## Fallback: the team wants the look of a specific site

In order of effort:

1. **Check the collection first.** Dozens of brands are there (Stripe, Apple, Spotify, Airbnb, Tesla and more). `curl` the raw URL with the brand's folder name.
2. **Browser extension**: install `bergside/design-md-chrome` (Chrome Web Store, open source), open the site, click Extract, save the result as `DESIGN.md`.
3. **Web generator**: paste the URL at `https://getdesign.md`, download the file.
4. **From source code**: Google's `google-labs-code/stitch-skills` repo has a `design-md` skill that writes a DESIGN.md from an existing codebase or a set of screenshots. Clone and run it if the team already has a reference project.
5. **Manual, 10 minutes**: take one screenshot of the reference site's home above the fold. Read it and fill this template into `DESIGN.md`:

```markdown
# Design: <reference site>
## Colors
- Background: #
- Surface (cards): #
- Text primary: #
- Text secondary: #
- Accent: #
## Typography
- Headings: <family>, weight, sizes used
- Body: <family>, 16px, line-height 1.5
## Shape
- Border radius: <px>
- Borders: <color, 1px> or none
- Shadows: none / soft
## Layout
- Max content width: <px>
- Section spacing: <px>
## Components seen
- Button: <shape, color, text style>
- Card: <padding, radius, border>
- Nav: <height, items, alignment>
```

Then continue at Step 3.

## Bonus: better-than-template UI

If the agent is Claude Code, the `frontend-design` plugin (`/plugin install frontend-design@claude-plugins-official`) produces interfaces well above generic AI output. Run it *after* `DESIGN.md` exists so it respects the tokens. Other agents: tell them "follow DESIGN.md strictly, avoid generic gradients and centered hero layouts, use the typography scale from the file".
