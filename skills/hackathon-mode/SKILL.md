---
name: hackathon-mode
description: Working posture for a two-day hackathon (NASA Space Apps 2026). Use when the team has chosen a challenge and starts building, or whenever the user says "hackathon mode", "we have N hours", "MVP", "ship it". Enforces no tests, no auth, no abstractions, mock data first, deploy in the first 2 hours, one feature at a time, and an opinionated two-lane stack (Vite + React + Tailwind for web, Python + Streamlit for data).
---

# Hackathon Mode

You are pairing with a team that has until **Sunday 11:59 PM local time** to submit a working project with a public link. Nothing you build will be maintained after that. The window is Saturday 9:00 AM to Sunday 11:59 PM local, about 39 hours. Optimize for *a demo that runs* and *a story that lands*, not for code quality.

## Posture (apply to every answer)

- **In 48 hours** here means the whole weekend; the clock for judging purposes is the ~39-hour window above.

- **Ship over perfect.** Working ugly beats elegant unfinished. Never refactor working code during the event.
- **No tests, no CI, no linting setup, no TypeScript strictness fights.** If the tool scaffolds them, leave them alone. Do not write tests unless the user asks.
- **No auth, no database, no user accounts.** State lives in memory, `localStorage`, or a JSON file. If the idea "needs" login, cut it: the judges see one demo, not a product.
- **No abstractions for the future.** One component file is fine with 300 lines. Copy-paste beats a premature helper. No folder structure debates.
- **Mock data first.** Before touching any NASA API, build the whole screen against `data/sample.json` with 5 to 20 realistic rows. Swap to the live source only after the screen works. If the live source fails Sunday, the mock still demos.
- **Deploy within the first 2 hours**, even if the page says "hello". Every later feature ships to the same URL. A public link that works is a hard requirement for judging; it cannot wait until Sunday night.
- **One feature at a time:** build → deploy → next. Never two half-features.
- **Ask one question, then default.** If the user is unsure, pick the simplest option, say which you picked, and move.
- **Error handling:** a `try/catch` that shows a friendly message and falls back to the sample data. Nothing more.

## The ladder (before writing anything)

1. Does this need to exist for the demo? If not, skip it and say so.
2. Can an existing library or component do it? Use it.
3. Can it be one file? Keep it one file.
4. Only then write the minimum that works.

## Stack: pick one lane in the first 10 minutes

### Lane A: web app (maps, dashboards, games, storytelling, anything visual)

```bash
npm create vite@latest app -- --template react
cd app && npm install && npm install tailwindcss @tailwindcss/vite
```

`vite.config.js`: add `import tailwindcss from '@tailwindcss/vite'` and `tailwindcss()` to `plugins`. In `src/index.css` put `@import "tailwindcss";` as the first line. Done, no config file.

Useful add-ons, only when the feature needs them: `leaflet` + `react-leaflet` (2D maps), `three` + `@react-three/fiber` (3D), `recharts` (charts), `phaser` (2D games).

Deploy, choose one:

- **Vercel** (fastest, no config): `npx vercel` from the project root. The first run opens a browser login, so do it before the Sat 11:00 checkpoint. Accept defaults, then `npx vercel --prod`. Use the production URL (the one without a random hash) for the submission and open it in a private window: preview URLs can be protected by Deployment Protection.
- **GitHub Pages**: set `base: '/<repo-name>/'` in `vite.config.js`, `npm run build`, then push `dist/` with `npx gh-pages -d dist` (install with `npm i -D gh-pages`). Enable Pages on the `gh-pages` branch in repo settings.

### Lane B: data app (analysis, time series, "detect a trend", anything where Python wins)

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install streamlit pandas requests plotly
streamlit run app.py
```

One `app.py`, `st.sidebar` for inputs, `st.plotly_chart` or `st.map` for output. Add `xarray` + `netCDF4` only if the dataset is NetCDF/HDF; add `geopandas` only for shapefiles.

Deploy: push to a public GitHub repo with `requirements.txt`, then **Streamlit Community Cloud** (share.streamlit.io) → New app → pick the repo. Free, takes 3 minutes. Alternative: Hugging Face Spaces with the Streamlit SDK.

### Deploying with someone who does not code

Most teams have one person running these commands who has never deployed anything. Before each deploy command, say in one plain sentence what it does and what they will see ("this uploads the site; a browser tab will open asking you to log in to Vercel; after that, a link appears in the terminal"). After it runs, tell them which line of the output is the link and ask them to open it in a private window. No explanation of what a build is unless they ask.

When the deploy breaks, check these first, in order:

- **Vercel asks to log in again or hangs on login.** Run `npx vercel login`, finish it in the browser tab, then run `npx vercel --prod` again.
- **Vercel build fails with a missing module.** The dependency was installed but not saved: `npm install <name>` without `--no-save`, commit `package.json` and `package-lock.json`, redeploy.
- **Vite site deploys but shows a blank page.** On GitHub Pages, `base` in `vite.config.js` does not match the repo name. On Vercel, a hard-coded path starts with `/` and should be relative. Open the browser console: a 404 on a `.js` file confirms it.
- **Streamlit Cloud says it cannot find `requirements.txt`** or fails on import. The file must be at the repo root and list every `import` in `app.py`; `pip freeze > requirements.txt` is the fast fix. Push and click Reboot app.
- **GitHub Pages shows a 404.** Settings → Pages → Source must be the `gh-pages` branch, root folder. The first publish takes up to 2 minutes.
- **Environment variable or API key missing in production.** Local `.env` files do not travel. Add the variable in the provider's dashboard (Vercel: Settings → Environment Variables; Streamlit: App settings → Secrets) and redeploy. Keep `DEMO_KEY`-class keys out of the browser bundle (see the `nasa-data` skill).

### Mixed team

Lane A for the demo, Lane B as a one-off script that fetches real NASA data and writes `data/sample.json` the web app reads. A JSON refreshed by that script counts as "live NASA data wired". Do not wire them at runtime.

## NASA data rules that cannot be cut

- The project must use **at least one NASA dataset or resource** to be eligible for a Global Award. Pick it from the challenge page's "Resources" list (in `docs/*/challenges/` of the kit, or the official page). Write it down in `SOURCES.md` the moment you choose it, with the URL.
- Get API keys in hour 1 (the FIRMS MAP_KEY arrives by email; NASA api.nasa.gov keys too). Never ship a key in the client bundle: fetch with a script and commit the resulting JSON, or use a serverless function with an env var.
- Everything on the submission page and in linked materials must be in **English**. Code comments and commit messages can be anything.
- No NASA logos, insignia or "Space Apps" branding inside the app or the demo. Say "Built with NASA data" in text instead.
- If you use AI to generate images, video or audio, keep a visible watermark or caption ("AI-generated") and disclose it on the submission form. Code written with AI assistance is fine; just mention it in the "Use of AI" field.
- Demo material: a video of **at most 30 seconds** or a deck of **at most 7 slides**. Plan the demo around what already works, not around what you hope to finish.

## Timeline checkpoints (local time)

| When | Must be true |
| --- | --- |
| Sat 11:00 | Challenge chosen, lane chosen, repo created, `hello` deployed at a public URL |
| Sat 14:00 | Screen works end to end on sample data |
| Sat 19:00 | Live NASA data wired for the one core feature (use the `nasa-data` skill), or decision made to stay on a curated sample, documented |
| Sun 12:00 | Feature freeze. Only fixes, copy and visuals from here |
| Sun 16:00 | Demo recorded or slides done. Submission form drafted (use the `submit-and-demo` skill) |
| Sun 20:00 | Submitted. The remaining hours are a buffer, not build time |

If a checkpoint slips by more than 2 hours, cut scope until it holds. Cutting is the plan, not the failure.

## Files to keep from hour one

- `README.md`: one paragraph on what it does, the public URL, how to run locally.
- `SOURCES.md`: every dataset, API, library, image, font and DESIGN.md used, with URL and license. This becomes the "References" field on the submission form, which is required.
- `data/sample.json` (or `.csv`): the mock that always works.

## When the user asks for something out of posture

Tests, auth, database, microservices, perfect types, i18n, accessibility audit, "clean architecture": answer in one line why it does not help the demo, offer the lazy equivalent, and move on. If the user insists, do it without re-arguing.
