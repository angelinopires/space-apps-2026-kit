---
name: submit-and-demo
description: Writes the NASA Space Apps 2026 submission page and demo for a hackathon project. Use on the last day, when the user says "submit", "submission", "demo", "video", "slides", "pitch", or asks what the judges want. Produces every form field in English mapped to the 5 judging criteria, a 30-second video script or 7-slide outline within the official limits, and runs the eligibility checklist (public links, English, under-18 likeness, AI disclosure, NASA data, References).
---

# Submit and Demo

Deadline: **Sunday, November 15, 2026, 11:59 PM** in the Local Event's time zone (Universal Event: the Team Owner's time zone). Only the Team Owner can submit, from the team page on spaceappschallenge.org. Judging starts Monday. The submission page is what the judges read; the demo is what they watch. Both must stand alone.

## Step 1: collect inputs (one message)

Ask for, or read from the repo if present:

1. `CHALLENGE.md` or the challenge name.
2. `README.md` and the public URL of the deployed project. Open the URL and confirm it loads without login.
3. What actually works today (not what was planned). Three bullets max.
4. `SOURCES.md`: every NASA dataset, other dataset, library, font, DESIGN.md and image used.
5. Which parts used AI (code assistance, generated text, images, audio, video).
6. Team name, and whether anyone on the team is under 18 or whether any under-18 person appears in demo material.
7. Demo format chosen: 30-second video or 7-slide deck.

## Step 2: write the submission fields

Write in English, plain and concrete. Judges read dozens of these; the first sentence of each field carries the score. Save everything to `SUBMISSION.md` so the Team Owner can paste it.

| Field | Length | What to write | Criterion it feeds |
| --- | --- | --- | --- |
| Project name | 2 to 4 words | Memorable, no NASA branding, no "Space Apps" | Presentation |
| High-level summary | 2 to 4 sentences | What it does, who it is for, which NASA data it uses, why it matters. A judge who reads only this must understand the project | Impact, Relevance |
| Link to demo | URL | Video (YouTube or similar, public or unlisted, 30 s max) or slides (Google Slides, PDF link, 7 slides max). Test the link in a private window | Presentation |
| Link to final project | URL | The live app URL. If the form takes only one link, use the app and link the repo from its README | Validity |
| Detailed description | 4 to 8 short paragraphs | What it does and how it works; what benefits it brings; what you hope to achieve; tools, languages, hardware used; how the solution addresses the challenge. One short paragraph per question | All five |
| NASA data | List | Each NASA dataset or resource by name with URL and one line on how it is used. At least one is required for Global Award eligibility | Relevance, Validity |
| Space Agency Partner and other data | List | Non-NASA datasets, libraries, APIs, fonts, the DESIGN.md source | Validity |
| Use of Artificial Intelligence | 1 to 3 sentences | Name the tools and what they produced (code assistance, text, images). If AI generated any image, audio or video, state that it is watermarked or captioned. Judges do not see this field, so repeat the acknowledgment in one line of the Detailed description | Eligibility |
| References | List | Everything from `SOURCES.md` with URLs and licenses. This field is required | Eligibility |

### The five criteria, scored 1 to 5 each

- **Impact**: who benefits, how much, and how soon. Name the user and the scale, even if estimated.
- **Creativity**: what is new about the approach or the combination. One concrete contrast ("existing tools show X; this shows Y").
- **Validity**: does it work, is it technically sound, is the science right. Mention the data processing steps in one line each; link the live app.
- **Relevance**: does it answer the challenge as written and does it use NASA data in a way that matters. Quote the challenge's own objective in one phrase and show the match. If the MVP covers only part of the ask, say so in one sentence and name the next step; an honest scope beats an overclaim the judges can see through.
- **Presentation**: clarity of the page and the demo. Short sentences, no jargon without a gloss, one idea per paragraph.

Write each field, then re-read it against the criterion in the last column. If a field does not move its criterion, rewrite it.

## Step 3: the demo

### Option A: 30-second video (recommended, judges watch more than they read)

Script by timestamp; speak or caption in English (voice in another language is fine with English subtitles burned in):

```
[0:00-0:03] Hook: the problem in one sentence, over a real screen of the app.
[0:03-0:07] Challenge name and project name, as a caption.
[0:07-0:20] The app doing its one core thing, live: click, result, the NASA data visibly in use. One interaction only; a filter plus a chart is already two, pick the stronger. No menus, no loading screens.
[0:20-0:26] Who it helps and what changes for them.
[0:26-0:30] Team name, "Built with NASA data", public URL as a caption.
```

Recording: screen record at 1080p, trim to 30.0 s or less (31 s is over), export MP4, upload to YouTube as unlisted or public, copy the link. Use the computer's built-in recorder (macOS: Shift+Cmd+5; Windows: Win+G; Linux: OBS). Add subtitles in the editor or with YouTube's subtitle tool. Check the final length in the uploaded video's player, not the editor.

### Option B: 7 slides

```
1. Title: project name, challenge name, team name, public URL
2. The problem, in one sentence and one image
3. The solution: one screenshot of the app with 3 labels
4. How it works: NASA data in → processing → what the user sees (one diagram)
5. Demo: 2 screenshots of the core feature with a one-line caption each
6. Impact: who benefits, what changes, what comes next
7. Team members, "Built with NASA data", links, licenses of data used
```

Export to PDF, upload to the repo or Google Drive with "anyone with the link can view", and test in a private window. Slide 8 does not exist; appendix slides count.

Write the script or outline to `DEMO.md`.

## Step 4: eligibility checklist

Run through every line; fix before submitting:

- [ ] Public URL of the app opens in a private browser window without login and does not crash on first load. On Vercel, use the production URL, not a preview URL (previews can be protected).
- [ ] Repository is public and its README states what the project does and how to run it.
- [ ] Demo is at most 30 seconds or at most 7 slides, in English or with English subtitles, link opens without login.
- [ ] Every field of the submission page is in English.
- [ ] At least one NASA dataset or resource is named in the "NASA data" field with URL, and it is actually used in the app.
- [ ] The References field lists every data source, library, font, design reference and image with URL and license.
- [ ] "Use of AI" field filled. Any AI-generated image, audio or video carries a visible watermark or caption.
- [ ] No NASA logos, insignia or Space Apps branding in the app, video or slides.
- [ ] No image or video of anyone under 18 anywhere in the materials, even if on the team.
- [ ] No copyrighted music or images without license in the video or slides.
- [ ] Team page lists every member, and the Team Owner is the one submitting.
- [ ] The two form checkboxes are ticked: you read the submission requirements and accept the Terms; the work is original and every external resource is listed in References.
- [ ] Submitted before 11:59 PM local time, with at least 1 hour of margin. Submitting at 11:58 is a plan to miss it.

## Step 5: after submitting

Tell the team to take a screenshot of the confirmation, keep the app deployed and the repo public until at least January 2027 (Global Winners are announced on January 26, 2027), and not to change the public URL. Edits after the deadline are not allowed; fixes go in a branch, not in the deployed demo.
