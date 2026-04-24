# matilha-growth-pack

> **You lead. Agents hunt.**
> Matilha companion pack — 20 growth and product-strategy skills.

> 🏠 **This is a companion pack.** The official matilha entry point is [**danilods/matilha-skills**](https://github.com/danilods/matilha-skills) — start there for the full install guide + ecosystem overview. Install this pack only after the core is set up (via `/matilha-install` in Claude Code, or the explicit commands below).

## What this is

`matilha-growth-pack` extends [Matilha](https://github.com/danilods/matilha-skills) with growth and product-strategy skills. Each skill fires automatically when user intent matches — picking pricing triggers `growth-pricing-psychology` + `growth-value-metric`; designing onboarding triggers `growth-activation-aha-moment`; researching motivation triggers `growth-jtbd-forces`.

This pack is the second shipped companion pack (after [matilha-ux-pack](https://github.com/danilods/matilha-ux-pack)). Together they cover behavioral science from two lenses: UX execution (ux-pack) and product/business strategy (growth-pack).

## Install

### Claude Code (recommended: user scope)

Install at user scope so the pack is available in every workspace, not just per-project:

```
/plugin marketplace add danilods/matilha-growth-pack
/plugin install matilha-growth-pack@matilha-growth-pack --user
```

(If `--user` is not recognized, use the interactive `/plugin` menu and select **user scope**.)

When [matilha core](https://github.com/danilods/matilha-skills) is also installed, its `matilha-compose` gateway auto-detects this pack via plugin-namespace inspection (`matilha-*-pack`) and injects pack-aware preamble into brainstorming sessions whenever user intent touches growth, activation, retention, pricing, or JTBD concerns. The pack also works standalone — skills activate via their own descriptions when intent matches.

Or locally during development:

```
/plugin install /path/to/matilha-growth-pack
```

### Cursor

Same `/plugin install` flow — compatible with Claude Code's `.claude-plugin/plugin.json` format.

### Codex CLI

Point at the repo; enable `multi_agent = true` in `~/.codex/config.toml` if you want subagent dispatch.

### Gemini CLI

Install as an extension; `gemini-extension.json` lands in a follow-up release (Claude Code + Cursor + Codex ready out of the box).

## Skills (20 total)

**Acquisition & metrics (3):** `growth-aarrr-funnel`, `growth-north-star-metric`, `growth-instrumentation-plan`.

**Product-led growth (3):** `growth-plg-strategy`, `growth-activation-aha-moment`, `growth-viral-loops`.

**JTBD & positioning (4):** `growth-jtbd-forces`, `growth-positioning-strategy`, `growth-category-creation`, `growth-icp-definition`.

**Behavioral frameworks — product angle (4):** `growth-hook-model-product`, `growth-fogg-bmap-feasibility`, `growth-octalysis-drives`, `growth-peak-end-journey`.

**Pricing & monetization (3):** `growth-pricing-psychology`, `growth-freemium-strategy`, `growth-value-metric`.

**Retention & moat (3):** `growth-retention-curves`, `growth-churn-diagnostics`, `growth-network-effects`.

Each skill is derived from 2-5 wiki pages plus source attribution. See individual `skills/<slug>/SKILL.md` files.

## Integration with Matilha core

When `matilha-skills` (Matilha core) is installed, core skills delegate automatically:

- `matilha-scout` (Phase 10 research) → `growth-jtbd-forces`, `growth-icp-definition`, `growth-positioning-strategy`.
- `matilha-plan` (Phase 20-30 spec authoring) → `growth-aarrr-funnel`, `growth-value-metric`, `growth-pricing-psychology`.
- `matilha-design` (cross-phase) → complements `matilha-ux-pack` when product-level strategy intersects UX execution.

If Matilha core is absent, pack skills still work standalone.

## Overlap with matilha-ux-pack

Four skills derive from wiki pages that ux-pack also uses (Hook Model, Fogg B=MAP, Octalysis, Peak-End). They cover a DIFFERENT triggering intent:

| growth-pack skill | ux-pack sibling | Distinction |
|---|---|---|
| `growth-hook-model-product` | `ux-variable-rewards` | Product-flow habit formation vs feature-level engagement mechanics |
| `growth-fogg-bmap-feasibility` | (none) | Strategic feasibility gate |
| `growth-octalysis-drives` | `ux-intrinsic-motivation` | Gamification architecture vs SDT at feature level |
| `growth-peak-end-journey` | `ux-emotion-in-ui` | Journey satisfaction vs tone per moment |

Install both packs for complementary coverage.

## Attribution

Skills synthesize principles from:

- *Hooked* (Nir Eyal, 2014) and *Indistractable* (2019).
- JTBD canon (Clayton Christensen, Bob Moesta, Chris Spiek).
- Positioning canon (Al Ries, April Dunford).
- *Actionable Gamification* (Yu-kai Chou, Octalysis).
- *Thinking Fast and Slow* (Daniel Kahneman, System 1/2 + Peak-End).
- BJ Fogg's Behavior Model (B=MAP, 2019).
- AARRR Pirate Metrics (Dave McClure).
- PLG canon (Wes Bush, Bob Moore).

Skill content is Danilo's original synthesis via Obsidian wiki paraphrase. Source books are credited but not quoted verbatim.

See `docs/wiki-ingestion-workflow.md` for the authoring discipline.

## Contribute

Pack is open source. To propose a new skill or refine one:

1. `docs/wiki-ingestion-workflow.md` in this repo.
2. `matilha-skills/docs/matilha/skill-authoring-guide.md` (upstream style guide).
3. `matilha-skills/docs/matilha/pack-authors.md` (upstream pack-author contract).

## License

MIT.
