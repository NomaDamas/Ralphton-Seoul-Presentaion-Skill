---
name: ralphthon-seoul-mid-presentation-en
description: Interview-driven slides-grab workflow for the Ralphthon Seoul mid-presentation format. Use when the user wants an English Ralphthon deck that gathers required answers first, derives the outline, generates HTML slides, validates them, builds the viewer, and launches the slides-grab editor.
metadata:
  short-description: English Ralphthon mid-presentation slides-grab workflow
---

# Ralphthon Seoul Mid-Presentation (English)

Use this skill when the user wants to create a Ralphthon Seoul mid-presentation deck in English with `slides-grab`.

## Goal
Complete the full pre-export flow:
1. confirm `slides-grab` setup,
2. run a required interview,
3. derive `slide-outline.md`,
4. generate HTML slides,
5. validate and build the viewer,
6. **launch the editor after HTML slide creation**.

Do **not** skip the interview. Do **not** stop at the outline. Do **not** stop at generated HTML. After the HTML slides are created, you must mention and run `slides-grab edit --slides-dir <path>`.

## Required setup check
Before interviewing, verify the environment.

1. Check whether `slides-grab` is available:
   - `slides-grab --help`
   - or `npm exec -- slides-grab --help`
2. If unavailable, guide the user through the standard setup from `references/slides-grab-setup.md`.
3. If the Codex `slides-grab` skills are missing, tell the user to install them with the official npm package flow and restart Codex:
   - `npm install slides-grab`
   - `npx playwright install chromium`
   - `npx skills add ./node_modules/slides-grab -g -a codex --yes --copy`
4. Resume only after the CLI is available.

## Mandatory interview
Ask the user questions before outlining. Use `references/interview-checklist.md` as the checklist.

At minimum, collect or confirm:
- project name
- team / members / GitHub URL
- target user and problem
- frequency and pain level of the problem
- one personal story or user case that makes the problem convincing
- one-sentence product definition
- key workflow or features to show
- which AI agents / tools were used
- what process kept the team “serious about Ralph” / continuously shipping
- optional current progress summary

If any required item is missing, ask follow-up questions. Do not invent answers.

## Deck structure
Default to a concise deck aligned with the Ralphthon Seoul mid-presentation template:
1. Title slide — project, team, members, GitHub
2. Problem definition — who, what, frequency, pain, evidence/story
3. Solution / product — one-sentence definition and key workflow
4. Ralph setup / capability — AI agents, workflow, persistence strategy
5. Current progress — optional, include only if the user has meaningful updates

If the user gives enough material, you may split problem or solution into extra slides, but keep the story tight.

## Workflow
1. Interview the user until the minimum required inputs are grounded.
2. Create `slide-outline.md`.
3. Show the outline briefly and get explicit approval before designing slides.
4. Use `decks/<deck-name>/` as the slides workspace.
5. Generate `slide-XX.html` files.
6. Run `slides-grab validate --slides-dir <path>`.
7. Fix HTML/CSS until validation passes.
8. Run `slides-grab build-viewer --slides-dir <path>`.
9. Report where the viewer was built.
10. **Run `slides-grab edit --slides-dir <path>` after the HTML slides are ready.** Mention clearly that the editor launch is mandatory in this workflow.

## Rules
- Keep the workflow in English unless the user explicitly asks otherwise.
- Follow the Ralphthon template priorities: problem attractiveness, solution effectiveness, Ralph capability.
- Prefer concrete user pain and workflow evidence over slogans.
- Keep slides concise and pitch-oriented.
- Do not start export in this skill. This skill ends after the editor is launched.
- If the user wants export later, hand off to the standard `slides-grab-export` workflow.

## References
- `references/interview-checklist.md`
- `references/slides-grab-setup.md`
