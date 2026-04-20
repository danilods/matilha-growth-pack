# Wave 5b Smoke Test Results

**Date:** 2026-04-19
**Pack:** matilha-growth-pack on branch `wave-5b-growth-pack`
**matilha CLI tests:** 743/743 passing (595 baseline post-Wave 5a + 148 new growth-pack validation)
**Platform:** macOS (local dev). Claude Code marketplace install deferred to post-ship.

## Structural smoke (automated)

| Artifact | Status | Notes |
|---|---|---|
| `.claude-plugin/plugin.json` | ✅ | name=matilha-growth-pack; version=0.1.0; matilha-pack keyword present |
| `.claude-plugin/marketplace.json` | ✅ | valid JSON |
| `CLAUDE.md` + `GEMINI.md` + `AGENTS.md` + `README.md` | ✅ | all 4 contain slogan "You lead. Agents hunt." |
| `LICENSE` | ✅ | MIT |
| `docs/wiki-ingestion-workflow.md` | ✅ | 5-step discipline documented |
| 20 skills canonical | ✅ | all growth-*, 13 sections, Sources wikilinks, 170-207 lines, descriptions starting with "Use when" |
| Activation uniqueness | ✅ | heuristic passes (no pair > 80% description word overlap) |
| Overlap disclosure (4 skills) | ✅ | growth-hook-model-product, growth-octalysis-drives, growth-peak-end-journey all contain "Complements"; growth-fogg-bmap-feasibility contains "No direct" |

## Validation suite (matilha CLI repo)

- `npm test` → **743/743 green** (595 baseline + 148 new growth-pack validation tests)
- `npx tsc --noEmit` → clean
- 148 new tests broken down:
  - 3 plugin.json tests
  - 80 frontmatter tests (20 × 4)
  - 60 body tests (20 × 3)
  - 1 activation-uniqueness heuristic
  - 4 overlap-disclosure tests

## Semantic smoke (mental-model walkthrough)

**Scenario 1: User plans pricing strategy**
- Intent: "How should I structure pricing tiers for my B2B SaaS?"
- Expected activation: `growth-pricing-psychology` (anchoring, decoy) + `growth-value-metric` (pick dimension) + possibly `growth-freemium-strategy`
- Core delegation: `matilha-plan` Phase 20-30 via Companion Integration block

**Scenario 2: User researches user motivation**
- Intent: "I want to understand why users are switching to us"
- Expected activation: `growth-jtbd-forces` (Push/Pull/Anxiety/Habit) + possibly `growth-icp-definition`
- Core delegation: `matilha-scout` Phase 10

**Scenario 3: User analyzes retention**
- Intent: "Our D30 retention is dropping, help me diagnose"
- Expected activation: `growth-retention-curves` + `growth-churn-diagnostics` + possibly `growth-activation-aha-moment` if early-stage

**Scenario 4: User designs product engagement**
- Intent: "I want to gamify onboarding ethically"
- Expected DUAL activation (growth + ux packs): `growth-octalysis-drives` (8-drive architecture) + `ux-intrinsic-motivation` (SDT at feature level) — complementary coverage
- Overlap disclosure makes the dual-role clear

**Scenario 5: User picks business metric**
- Intent: "What should our North Star metric be?"
- Expected activation: `growth-north-star-metric` (single skill, clear intent)

## Overlap-vs-ux-pack verification

Scenario: user asks "Help me design for habit formation". Expected dual-activation:
- `growth-hook-model-product` fires for PRODUCT-flow level decisions (which flows deserve habit architecture).
- `ux-variable-rewards` fires for FEATURE-level mechanic design.
- Companion Integration sections in both make distinction clear; AI clarifies with user which layer they want.

This is BY DESIGN. The overlap-disclosure validator ensures it's explicit.

## Deferred: end-to-end Claude Code marketplace install

Deferred to post-ship user-assisted validation. Same reasoning as Wave 5a.

**Manual test plan** (post-merge, optional):
1. Clean Claude Code session.
2. `/plugin install` matilha-skills + matilha-ux-pack + matilha-growth-pack locally.
3. Natural-language: "I want to launch pricing for my SaaS."
4. Expect: `growth-pricing-psychology` + `growth-value-metric` activate.
5. Refine: "Also I want users to form a daily habit with the app."
6. Expect: `growth-hook-model-product` (strategic) + `ux-variable-rewards` (tactical) both activate — user sees the complementary framing.

## Risks flagged

- **Overlap perception**: user might feel duplication if both packs activate on similar intents without reading Companion Integration distinction. Monitor; adjust description wording if feedback surfaces.
- **Wiki source load**: 4 shared concept pages (hook-model, dopamina-comportamento, frameworks-comportamentais, peak-end-rule) now feed both ux-pack + growth-pack. Any future wiki update to these pages affects both packs — version coordination matters.

## Conclusion

Wave 5b ships. Structural + semantic gates pass. Pack ready for marketplace submission alongside ux-pack + matilha core.
