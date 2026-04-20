# Wiki Ingestion Workflow

> How to synthesize a Matilha pack skill from the Obsidian wiki.

## Why this exists

The `matilha-growth-pack` skills are derived from Danilo's Obsidian wiki, which is itself a curated paraphrase of source books (Eyal, Moesta, Ries, Chou, Kahneman, Fogg, McClure, Bush, etc.) and behavioral-economics literature. This doc codifies the discipline so that:

1. Future pack authors (including other Matilha packs) reproduce the same discipline.
2. Attribution is consistent — always 3 layers of remove from source books.
3. Activation is reliable — every skill has a distinct triggering intent.
4. Skill style follows `matilha-skills/docs/matilha/skill-authoring-guide.md`.

## The 5-step process per skill

### 1. Select triggering intent

From the pack's skill inventory (in the spec or `README.md`), pick one row. The row's activation description is the contract — the Skill tool matches this against user intent.

Example: `growth-jtbd-forces` → "Use when researching user motivation — map Moesta's Push, Pull, Anxiety, Habit forces of progress."

### 2. Load wiki sources

Read the 2-5 wiki pages listed in the skill's source mapping. Note:

- Key principles (what the skill is teaching).
- Concrete examples from the wiki or source books (which you'll rephrase).
- Citations back to the original source books.

Example sources for `growth-jtbd-forces`:
- `~/Documents/Memory/Memory/wiki/concepts/jtbd-positioning.md`
- `~/Documents/Memory/Memory/wiki/sources/product-htrategy.md`

### 3. Paraphrase + synthesize

Draft the skill body in Matilha's voice. Principles:

- **Paraphrase always** — do not copy source-book sentences. Do not copy wiki-page sentences verbatim either. Aim for 3 layers of remove.
- **Include ONE concrete example** per principle (e.g., "When a user cancels a gym membership after 3 weeks, Push = body image concern, Pull = convenience of home workouts, Anxiety = fear of looking bad at gym, Habit = TV after work. The Push/Pull won; Anxiety/Habit lost.").
- **Cite inline with wikilinks**: "(see `[[concepts/jtbd-positioning]]` for full Forces treatment)".
- **Close the body with a pointer** back to the Matilha core skill that most likely invokes this specialist (`matilha-scout`, `matilha-plan`).

### 4. Validate against the style guide

Check:

- [ ] Frontmatter matches `matilha-skills/docs/matilha/skill-authoring-guide.md` strict schema: `name`, `description` starting with "Use when" or "When", `category: growth`, `version: "1.0.0"`, `requires: []`, `optional_companions: []`.
- [ ] Body has all 12 required sections (When this fires, Preconditions, Execution Workflow, Rules: Do, Rules: Don't, Expected Behavior, Quality Gates, Companion Integration, Output Artifacts, Example Constraint Language, Troubleshooting) + mandatory `## Sources` section (13th).
- [ ] Mandatory `## Sources` section: 2-5 wikilinks in `[[wiki-path]]` format + book-attribution note.
- [ ] Body length 150-300 lines.

### 5. Cross-check activation uniqueness

`grep -r "^description: " skills/*/SKILL.md` and visually scan. Also cross-check against `matilha-ux-pack` skills — this pack has 4 intentional overlap points:

- `growth-hook-model-product` vs `ux-variable-rewards`: product flow vs feature mechanic.
- `growth-octalysis-drives` vs `ux-intrinsic-motivation`: 8-drive gamification vs SDT per feature.
- `growth-peak-end-journey` vs `ux-emotion-in-ui`: journey satisfaction vs UI tone.
- `growth-fogg-bmap-feasibility` has no direct ux overlap (foundational framework).

Each overlap skill's `## Companion Integration` section MUST state: "Complements `matilha-ux-pack:<slug>` at <angle>."

## Example: how `growth-jtbd-forces` was authored

Approx 30-minute process:
1. Selected intent: "researching user motivation, mapping Forces of Progress" (from inventory).
2. Read `concepts/jtbd-positioning.md` + `sources/product-htrategy.md` (12 minutes).
3. Drafted body sections — synthesized Push/Pull/Anxiety/Habit with Moesta's "hired/fired" framing (15 minutes).
4. Added Sources + validated 12 sections + 150-300 lines (2 minutes).
5. Cross-checked against other JTBD-adjacent skills (`growth-icp-definition`, `growth-positioning-strategy`) — narrowed triggering intent to "researching motivation" (not "defining ICP" or "positioning") (1 minute).

## When to promote to a meta-skill

If future Matilha packs (harness, security, etc.) reveal this workflow as repetitive + formulaic, consider promoting to a `matilha-wiki-ingest` meta-skill. That skill would read a wiki page URL, prompt for triggering intent, and generate a draft SKILL.md body.

Wave 5b continues to ship this as documented discipline.
