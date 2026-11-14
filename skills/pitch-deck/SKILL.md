---
name: pitch-deck
description: Writes the live pitch for a NASA Space Apps 2026 team's local event presentation (the one in front of local judges, separate from the 7-slide or 30-second submission demo). Use when the team says "pitch", "presentation", "local event", "we present tomorrow", "how many minutes do we have", or asks for slides for the judges. Asks the Local Lead's format first (minutes, Q&A, slides or not), reads README, SOURCES.md, SUBMISSION.md and DEMO.md, and returns one block per slide with title, up to three bullets, what the presenter says and how many seconds it takes, ready to paste into Google Slides, plus the five questions judges ask.
---

# Pitch Deck

Goal: a timed script the team can rehearse twice and present once, built from files the project already has. The submission demo (7 slides or 30 seconds, `submit-and-demo` skill) is for judges reading online. This pitch is for the room. Different length, same story.

## Step 1: get the format (one message, do not skip)

There is no official format for the local presentation. Each Local Lead sets it, and it ranges from 3 minutes with no questions to 10 minutes with 5 of Q&A. Ask:

1. How many minutes for the pitch, and is there Q&A after? If they do not know, tell them to ask the Local Lead now and default to 4 minutes plus 2 of Q&A.
2. Slides allowed? Projector, their own laptop, or a PDF sent ahead? Default: slides from their laptop.
3. Language of the room. Slides stay in English (the submitted material must be, and the same deck gets reused); the spoken part is whatever the judges speak.
4. Live demo allowed and is the internet reliable there? Default: show a screen recording or screenshots, never depend on the venue Wi-Fi.
5. Who presents. One voice for the story, a second person only for the demo. Three presenters in 4 minutes is a handoff exercise, not a pitch.

## Step 2: read the project

Read, in this order, and do not ask for anything that is in them:

- `CHALLENGE.md`: challenge name and the objective in the challenge's own words.
- `README.md`: what it does, the public URL.
- `SUBMISSION.md` (from `submit-and-demo`): the summary, the NASA data field, the impact paragraph. Reuse the sentences; judges hearing the same claim they read builds trust.
- `SOURCES.md`: the NASA datasets by name.
- `DEMO.md`: the screens already chosen for the video or slides.

If `SUBMISSION.md` does not exist yet, stop and run `submit-and-demo` first. The pitch is downstream of the submission, not a rewrite of it.

## Step 3: fit the story to the clock

Allocate seconds first, then write. Whatever the total, the demo gets about 40%, and the opening gets the problem, never the team.

| Section | Share | 3 min | 4 min | 7 min | What goes in it |
| --- | --- | --- | --- | --- | --- |
| Hook | 10% | 18 s | 25 s | 40 s | One sentence about who has the problem and what it costs them. A number if you have one. No "hi, we are team X". |
| Challenge and solution | 15% | 27 s | 36 s | 60 s | Challenge name, project name, what it does in one sentence. |
| Demo | 40% | 72 s | 96 s | 170 s | The one core feature, shown. Click, result, the NASA data visibly in use. Narrate what the judge is seeing, not how it was built. |
| NASA data and how it works | 15% | 27 s | 36 s | 60 s | Dataset names, where they come from, the one processing step that matters. This is the Validity and Relevance score. |
| Impact and what is next | 15% | 27 s | 36 s | 60 s | Who uses it Monday morning, what changes for them, the one next step if the project continued. |
| Close | 5% | 9 s | 10 s | 20 s | Project name, public URL, "built with NASA data", thank you. Team names on the slide, not spoken. |

Every pitch in this kit is 6 slides, whatever the duration; longer time means slower speech and a longer demo, not more slides. Reuse the submitted 7-slide deck when the team already has it: drop the "how it works" diagram into the data slide and you are at 6.

## Step 4: write the slides

One block per slide, in this exact shape, saved to `PITCH.md`. The team pastes the title and bullets into Google Slides (one slide per block, 24 pt minimum, one image per slide where noted) and reads the "Say" line from their phone or the speaker notes.

```
## Slide 1 · Hook · 25 s
Title: <the problem, as a statement, max 8 words>
Image: <a real photo or map of the problem; attribution in SOURCES.md>
Say: "<two sentences, spoken language, ends with the number or the person affected>"

## Slide 2 · Challenge and solution · 36 s
Title: <project name>
- <challenge name, official>
- <what it does, one line>
- <who it is for>
Say: "..."

## Slide 3 · Demo · 96 s
Title: <the core feature, as a verb phrase: "Pick a region, see 20 years of fires">
Image: <screen recording, or 2 screenshots side by side with a one-line caption each>
Say: "<narration that follows the screen: 'I draw a box over Mato Grosso. These are the active fires NASA's VIIRS sensor detected this week. Each bar is one day...'>"

## Slide 4 · NASA data · 36 s
Title: <"Built on <dataset>, <dataset>">
- <dataset name, sensor or mission, years covered>
- <second dataset, or the partner agency data>
- <the one processing step: harmonized, filtered, resampled, joined>
Say: "..."

## Slide 5 · Impact · 36 s
Title: <who benefits and what changes, max 8 words>
- <the user on Monday morning>
- <what they can do that they could not before>
- <next step if the project continued, one line>
Say: "..."

## Slide 6 · Close · 10 s
Title: <project name>
- <public URL>
- Built with NASA data
- <team name and members>
Say: "<one sentence, then stop. Do not say 'any questions', the host does that.>"
```

Writing rules:

- Spoken lines are spoken: contractions, short sentences, no word the presenter would not say to a friend. Read each "Say" aloud once; if it takes longer than the slot, cut it.
- Bullets are at most 3 and at most 8 words each. The slide is a prompt for the judge's eye, the presenter carries the content.
- One number per slide, maximum. Judges remember one.
- Zero jargon without a gloss in the same sentence ("hotspots, the pixels the satellite flags as burning").
- Honest scope. If the live demo covers one week of data and the challenge asks for twenty years, slide 4 says which years are in and slide 5 says how the rest would come in. Judges catch an overclaim in Q&A and it costs more than the gap.
- No NASA logos or Space Apps branding on the slides. The rule for the submission applies to anything the judges see.

## Step 5: Q&A sheet

Below the slides in `PITCH.md`, write the five questions this project will get, each with a two-sentence answer the team agrees on. Local judges follow the five official criteria, so the questions are predictable:

1. Impact: "Who would actually use this, and how many of them?"
2. Creativity: "What does this do that existing tools (FIRMS map, Worldview, a dashboard) do not?"
3. Validity: "How do you know the numbers are right?" (name the dataset, the filter, the known limitation)
4. Relevance: "The challenge asked for X; where is X?" (the honest-scope answer from slide 4)
5. Presentation and future: "What would you build next with one more week?"

Add a sixth if the team used AI heavily: "What did the AI do and what did you do?" Answer with the split, in one sentence each.

## Step 6: rehearse, then hand off

Tell the team to run it twice with a timer before the real thing: once reading, once from memory. The first run always goes long; cut the "Say" lines, never the demo. Fix the one slide that made the speaker stumble. Then export the deck to PDF as a backup and put it, with `PITCH.md`, in the repo. If the Local Lead asked for the deck ahead of time, send the PDF, not the Slides link.
