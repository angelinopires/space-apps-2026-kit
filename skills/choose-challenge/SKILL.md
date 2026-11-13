---
name: choose-challenge
description: Helps a NASA Space Apps 2026 team pick one of the 14 official challenges in under 30 minutes. Use when the team has not chosen yet, says "which challenge", "help us decide", or describes their skills and asks what to build. Collects team profile, scores the 14 challenges on 24-hour feasibility, data accessibility, team fit and story, and returns 2 or 3 candidates each with a 24-hour MVP, starting dataset, main risk and target award.
---

# Choose Challenge

Goal: in one conversation, go from "we have a team" to "we are building X". Do not list all 14 challenges to the user. Do the filtering yourself and present only the finalists.

## Step 1: collect the team profile (one message)

Ask these together, then proceed with whatever you get. Default any missing answer.

1. How many people, and what each is comfortable with (web front end, Python/data, design, game dev, writing/presenting, domain knowledge such as agriculture, health, astronomy).
2. Total build hours the team realistically has (default: 20 hours; the window is Sat 9:00 AM to Sun 11:59 PM local, about 39 hours).
3. Preferred lane: visual web app, data analysis, game, or no preference.
4. Comfort writing English for the submission (default: fine, the agent will draft it).
5. Anything they care about (a topic, a region, a dataset they already know). Passion is a real scoring factor: tired teams ship what they like.

## Step 2: load the challenge list

Read the challenge files, in this order of preference:

1. The kit cloned locally: `docs/en/challenges/README.md` (index) and the `NN-*.md` files for the shortlist. Portuguese equivalents in `docs/pt-br/desafios/`.
2. Raw from GitHub: `https://raw.githubusercontent.com/angelinopires/space-apps-2026-kit/main/docs/en/challenges/README.md` and `https://raw.githubusercontent.com/angelinopires/space-apps-2026-kit/main/docs/en/challenges/<file>.md`.
3. If neither is reachable, use the summary table below and link the official page `https://www.spaceappschallenge.org/2026/challenges/`.

## Step 3: score

For each challenge, score 1 to 5 on four axes and multiply:

- **Feasibility in 24 hours**: can one core feature be built and deployed by Saturday night? Challenges that ask for a game, a trainer or a simulation score high if the team can draw; challenges that need satellite image processing score low for teams without Python.
- **Data accessibility**: is the starting dataset a CSV/JSON/API that works in the browser, or is it HDF/NetCDF behind an Earthdata login? Read the challenge's Resources section. A ready API or a downloadable CSV scores 5; a 2 GB granule scores 1.
- **Team fit**: do the team's skills cover the core feature without learning a new stack?
- **Story**: can the result be shown in 30 seconds to a non-expert and make them say "oh"? Maps, before/after, games and anything with a human in the loop score high.

Rank by the product (max 625); discard anything below 40 as a sanity floor, plus anything the team said they dislike. Keep the top 3. Show the scores only if asked.

### Summary table (fallback and sanity check)

| # | Challenge | Lane | Typical 24 h MVP | Data entry point |
| --- | --- | --- | --- | --- |
| 01 | Abandoned but not Forgotten | web, storytelling | Interactive timeline or gallery of a decommissioned NASA mission with its legacy data | NASA image/video library, NTRS, mission archives |
| 02 | Earth System Trend Detective | data | Pick one variable (temperature, vegetation, sea ice) over 20 years for one region, plot the trend, let the user change region | Giovanni, NASA POWER, Earthdata |
| 03 | Junior Astronaut Mission Trainer | web, game | Browser mini-game or quiz for kids with 3 to 5 training "missions" using real mission facts | NASA images, astronaut training pages |
| 04 | Lunar Landing Site Navigator | web, map | 2D map of the Moon with CLPS landing sites, click for mission details | Moon Trek, LRO data, CLPS mission pages |
| 05 | Health Monitoring Software | data, web | Dashboard that ingests a sample of biometric data and flags out-of-range values with explanations | NASA OSDR, sample vitals |
| 06 | Dancing with the SARs | data | Before/after SAR image comparison for one event (flood, earthquake) with an explanation layer | ASF Vertex, NISAR/Sentinel-1 via ASF |
| 07 | Field Shift: Adapting Farms | data, web | Tool that shows how a crop's growing conditions in one region changed and suggests adaptation | NASA POWER, MODIS NDVI via AppEEARS |
| 08 | Flame in Freefall | web, education, data | Explainer or simulator of combustion in microgravity using ISS experiment data | PSI, NASA OSDR, ISS experiment pages |
| 09 | MODIS and VIIRS Hot Spots | data, map | Map of active fires for a region and date range with a filter and a trend chart | FIRMS area API (CSV, free MAP_KEY from firms.modaps.eosdis.nasa.gov/api/map_key/, max 5 days per call, call it from a script or serverless function, not from the browser) |
| 10 | Earth Analogs for Moon and Mars | web, map | Side-by-side of an Earth location and its Moon/Mars analog with terrain data | Earthdata, Moon Trek, Mars Trek |
| 11 | Martian Map | web, map, game | Mars map with layers (elevation, landing sites) and a "plan a route" mode | Mars Trek, MOLA, Quickmap |
| 12 | Planet X and SPHEREx | data, astronomy | Visualizer for SPHEREx-like sky survey data or an explainer of how an outer planet would be found | IRSA, SPHEREx pages, JPL Horizons |
| 13 | Space Mission Design Game | web, game | Browser game: budget, mass and science goals; player assembles a mission | Mission data from NASA pages, no heavy dataset |
| 14 | Earth Information Jukebox | web, creative | Turn a dataset (CO2, temperature, fires) into sound or visuals the user "plays" | Any single time series from Giovanni or POWER |

Beginner-friendly: 01, 03, 10, 13, 14. No heavy data: 01, 03, 13, 14. Heavy Earth data: 02, 06, 07, 09, 10. Map or 3D: 04, 10, 11. Health or text AI: 05, 08. Astronomy: 12.

## Step 4: present 2 or 3 finalists

For each finalist, one block:

- **Challenge** name, number and official link.
- **Why this team**: two lines tying their skills to the core feature.
- **24-hour MVP**: exactly 3 features, in build order. Feature 1 must be demoable alone.
- **Starting dataset**: name, URL (from the challenge's Resources section), format, and whether it needs an Earthdata login or an API key.
- **Main risk** and the cut you make if it bites.
- **Target award**: one of the 10 Global Awards (Best Use of Science, Best Use of Data, Best Use of Technology, Galactic Impact, Best Mission Concept, Most Inspirational, Best Storytelling, Global Connection, Art & Technology, Local Impact). Say which criterion it leans on.
- **Objectives check**: compare the 3 features with the challenge's Objectives. If the MVP covers less than the core ask, say what is missing and how the submission will phrase the scope honestly (this is the Relevance score).

Then recommend one, in one sentence, and ask the team to pick. No more than one round of follow-up; after that, go with your recommendation.

## Step 5: hand off

Once chosen, write `CHALLENGE.md` at the project root with the chosen block above plus the official challenge URL, then tell the user to continue with the `hackathon-mode` skill. If the kit is cloned, copy the challenge's Markdown file next to it so the agent can read the full Resources list offline.
