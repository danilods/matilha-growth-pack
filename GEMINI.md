# matilha-growth-pack — Matilha Companion Pack

> **You lead. Agents hunt.**
> A harness for building complex projects with AI.

`matilha-growth-pack` is a Matilha companion pack — 20 growth and product-strategy skills synthesized from Danilo's Obsidian wiki (product-growth-hacking, product-htrategy, AARRR, JTBD Forces of Progress, PLG strategies, behavioral frameworks like Fogg B=MAP and Octalysis, pricing psychology, retention analysis).

## How this loads in Gemini CLI

You are reading this because `matilha-growth-pack` is installed as a Gemini CLI extension. Gemini loads this file as context at session start. Skills live in `skills/`; when user intent matches a skill's description, invoke via `activate_skill` or follow the instructions directly from the SKILL.md body.

If `matilha-skills` (Matilha core) is also installed, its skills delegate here automatically for product/business questions. If Matilha core is absent, this pack's skills work standalone.

## What's inside

### 20 `growth-*` skills, grouped by triggering intent

**Acquisition & metrics (3):** `growth-aarrr-funnel`, `growth-north-star-metric`, `growth-instrumentation-plan`.

**Product-led growth (3):** `growth-plg-strategy`, `growth-activation-aha-moment`, `growth-viral-loops`.

**JTBD & positioning (4):** `growth-jtbd-forces`, `growth-positioning-strategy`, `growth-category-creation`, `growth-icp-definition`.

**Behavioral frameworks — product angle (4):** `growth-hook-model-product`, `growth-fogg-bmap-feasibility`, `growth-octalysis-drives`, `growth-peak-end-journey`.

**Pricing & monetization (3):** `growth-pricing-psychology`, `growth-freemium-strategy`, `growth-value-metric`.

**Retention & moat (3):** `growth-retention-curves`, `growth-churn-diagnostics`, `growth-network-effects`.

## Overlap discipline with matilha-ux-pack

Four skills share source material with matilha-ux-pack but cover a different triggering intent:

| growth-pack skill | ux-pack sibling | Distinction |
|---|---|---|
| `growth-hook-model-product` | `ux-variable-rewards` | Product flow level (strategic habit formation) vs feature-level engagement mechanics |
| `growth-fogg-bmap-feasibility` | (none direct) | Strategic feasibility gate for behavior-change features |
| `growth-octalysis-drives` | `ux-intrinsic-motivation` | Gamification 8-drive architecture vs SDT at feature level |
| `growth-peak-end-journey` | `ux-emotion-in-ui` | Session/journey satisfaction (memory bias) vs tone/copy per moment |

Both packs installed = complementary coverage, not redundancy.

## Companion integration (upward)

This pack is a **specialist** invoked by Matilha core skills. It does NOT invoke other packs in v0.1.0.

## Attribution

Skills are original synthesis. Wiki wikilinks cite curated paraphrases. Book attribution is credit only, never content transfer. See `docs/wiki-ingestion-workflow.md` for the authoring discipline.

## License

MIT.

## Links

- Core Matilha: https://github.com/danilods/matilha (CLI) + https://github.com/danilods/matilha-skills (plugin)
- First shipped pack: https://github.com/danilods/matilha-ux-pack
- This pack: https://github.com/danilods/matilha-growth-pack
