# Ralphthon Seoul Presentation Skills

Installable agent skills for creating **Ralphthon Seoul mid-presentation** decks with `slides-grab`.

## Included skills

- `ralphthon-seoul-mid-presentation-ko`
- `ralphthon-seoul-mid-presentation-en`

Both skills require the agent to:
1. verify `slides-grab` is available,
2. run a mandatory interview,
3. derive `slide-outline.md`,
4. generate HTML slides,
5. validate and build the viewer,
6. **launch the editor after HTML slide creation**.

## Install with Skills CLI

List available skills:

```bash
npx skills add NomaDamas/Ralphton-Seoul-Presentaion-Skill --list
```

Install the Korean skill to Codex:

```bash
npx skills add NomaDamas/Ralphton-Seoul-Presentaion-Skill --skill ralphthon-seoul-mid-presentation-ko -a codex
```

Install the English skill to Codex:

```bash
npx skills add NomaDamas/Ralphton-Seoul-Presentaion-Skill --skill ralphthon-seoul-mid-presentation-en -a codex
```

## slides-grab prerequisite

If `slides-grab` is not installed yet, use the official npm package flow:

```bash
npm install slides-grab
npx playwright install chromium
npx skills add ./node_modules/slides-grab -g -a codex --yes --copy
```

Then restart Codex.

## What the interview covers

The skills explicitly gather:
- project / team / members / GitHub
- user problem and pain
- frequency and evidence / story
- one-sentence product definition
- key workflow / features
- AI agents / tools used
- Ralph operating method
- optional current progress
