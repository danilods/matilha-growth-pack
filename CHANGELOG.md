# Changelog

## [0.1.0] — 2026-04-19 — Wave 5b: Second shipped Matilha companion pack

### Added

- **Pack infrastructure**: `.claude-plugin/plugin.json` + `marketplace.json` with `matilha-pack` keyword.
- **Context primers**: `CLAUDE.md` + `GEMINI.md` + `AGENTS.md` with pack-specific framing and slogan "You lead. Agents hunt."
- **20 skills** synthesized from Danilo's Obsidian wiki:
  - **Acquisition & metrics (3)**: growth-aarrr-funnel, growth-north-star-metric, growth-instrumentation-plan.
  - **Product-led growth (3)**: growth-plg-strategy, growth-activation-aha-moment, growth-viral-loops.
  - **JTBD & positioning (4)**: growth-jtbd-forces, growth-positioning-strategy, growth-category-creation, growth-icp-definition.
  - **Behavioral frameworks — product angle (4)**: growth-hook-model-product, growth-fogg-bmap-feasibility, growth-octalysis-drives, growth-peak-end-journey.
  - **Pricing & monetization (3)**: growth-pricing-psychology, growth-freemium-strategy, growth-value-metric.
  - **Retention & moat (3)**: growth-retention-curves, growth-churn-diagnostics, growth-network-effects.
- **`docs/wiki-ingestion-workflow.md`**: 5-step discipline for wiki-to-skill authoring.
- **`docs/smoke-results.md`**: Wave 5b structural + semantic smoke.
- Content-validation integration in `matilha` CLI (sibling-dir detection + 148 validation tests).

### Discipline

- Paraphrase-only body voice (3 layers of remove from source books — Eyal, Moesta, Ries, Chou, Kahneman, Fogg, McClure, Bush).
- Mandatory `## Sources` per skill with wikilinks + book attribution.
- **Overlap discipline with matilha-ux-pack**: 4 skills derive from wiki pages used in ux-pack (Hook Model, Fogg B=MAP, Octalysis, Peak-End). Each covers product/strategy angle, not ux/moment angle. Companion Integration sections explicitly declare distinction.
- Activation-uniqueness heuristic (descriptions don't overlap > 80% words).

### Notes

- Pack works standalone or in composition with matilha-skills (core) and matilha-ux-pack (first pack).
- When matilha-skills is installed, core skills (matilha-scout, matilha-plan, matilha-design) delegate automatically per Wave 4a companion contract.
- When matilha-ux-pack is also installed, overlap skills fire alongside their ux-pack siblings — complementary coverage by design.
- Pack skills do NOT delegate to other packs in v0.1.0. Future versions may add cross-pack integrations.
- Content breadth (AARRR + JTBD + positioning + behavioral frameworks + pricing + retention) together with matilha-ux-pack = unique depth in Claude Code / Cursor / Codex / Gemini ecosystems.
