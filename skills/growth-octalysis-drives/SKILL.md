---
name: growth-octalysis-drives
description: Use when gamifying product engagement — apply Yu-kai Chou's 8 Core Drives to design multi-dimensional motivation architecture with ethical framing.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team is designing system-level gamification across an entire
product — onboarding to long-term retention — rather than a single
badge or progress bar. Fires when motivation mechanics feel thin
("we added points"), when engagement is strong early but fades, or
when the product is being compared to category leaders with
sophisticated motivation architectures (Duolingo, Strava, LinkedIn).
This skill maps the 8 Core Drives across the product's lifecycle
phases with deliberate White Hat / Black Hat balance.

## Preconditions

- The product has observable user cohorts across multiple lifecycle
  phases (discovery, onboarding, scaffolding, endgame) or can
  reasonably segment users by tenure. Octalysis is a multi-phase
  diagnostic and needs phase evidence.
- The team has design and engineering bandwidth to build and tune
  motivation surfaces over a multi-quarter horizon. Octalysis is not
  a one-sprint project.
- Leadership accepts the ethical framing. Pure Black Hat architectures
  drive short-term urgency at the cost of long-term trust; a
  White-Hat-dominant system is strategically stronger.

## Execution Workflow

1. Use Read on product usage data, segmented by tenure. Identify which
   lifecycle phase shows the weakest retention — discovery (won't try
   it), onboarding (drops in first sessions), scaffolding (stops
   returning after novelty), or endgame (veterans disengage).
2. Map the current product against the 8 Core Drives. Epic Meaning &
   Calling (serving a greater cause), Development & Accomplishment
   (progress, mastery), Empowerment of Creativity (self-expression,
   feedback), Ownership & Possession (investment, collection), Social
   Influence & Relatedness (peers, mentors), Scarcity & Impatience
   (limited access, FOMO), Unpredictability & Curiosity (variable
   rewards), Loss & Avoidance (fear of losing progress). Note which
   drives are present, which are absent, which are over-relied-on.
3. Apply the White Hat / Black Hat lens. White Hat drives (Epic
   Meaning, Development, Empowerment, Ownership) generate long-term
   positive motivation. Black Hat drives (Scarcity, Unpredictability,
   Loss) generate short-term urgency but drain user reservoir if
   unchecked. Audit the balance.
4. Match drives to lifecycle phase. Discovery benefits from Epic
   Meaning and Unpredictability (why try this?). Onboarding benefits
   from Development and Empowerment (quick wins, visible progress).
   Scaffolding benefits from Ownership and Social Influence
   (investment, community). Endgame benefits from mastery identity
   and legacy (all drives in balance).
5. Check for over-justification risk. If intrinsic motivation already
   exists for an activity (users love the core workflow), layering
   extrinsic rewards can erode it (Ryan & Deci's over-justification
   effect). Gamify where intrinsic motivation is weak; leave alone
   where it is strong.
6. Design the architecture, not the veneer. Octalysis done right weaves
   drives into core product activity, not onto a "rewards tab." A
   gamification layer that users can ignore is a gamification layer
   that does not motivate.
7. Ship in phases. Start with the lifecycle phase showing the weakest
   retention and the drive most clearly absent. Measure. Expand to
   the next weak spot. Do not ship all 8 drives at once — the system
   becomes illegible.
8. Re-audit quarterly. Drives that worked in year one often fade as
   users mature; endgame users need different drives than onboarding
   users. Static gamification architectures decay.

## Rules: Do

- Map all 8 Core Drives against the current product before proposing
  additions. Gaps and over-reliance are both signal.
- Match drives to lifecycle phase. A drive that works in onboarding
  may not work in endgame and vice versa.
- Maintain White Hat dominance. Black Hat drives are legitimate tools
  for urgency but drain user reservoir if they dominate the system.
- Weave drives into core product activity, not onto a separate
  rewards layer users can ignore.
- Ship in phases, measure, then expand. All-at-once gamification is
  illegible and tunes itself poorly.

## Rules: Don't

- Don't add points and badges as a veneer on a product that does not
  need them. Over-justification erodes intrinsic motivation.
- Don't rely only on Black Hat drives (Scarcity, Unpredictability,
  Loss). They generate short-term engagement and long-term distrust.
- Don't design a single generic gamification layer across all users.
  Different lifecycle phases need different drives.
- Don't confuse Octalysis with feature-level variable rewards. This
  skill operates at system architecture level across the product;
  feature-level reward mechanics live elsewhere.
- Don't skip the over-justification check. Gamifying an intrinsically
  motivated workflow is actively harmful.

## Expected Behavior

After applying the skill, the team has a drive-by-phase map that
shows which of the 8 drives are active in discovery, onboarding,
scaffolding, and endgame. Gaps (missing drives in the weakest phase)
become the prioritized gamification backlog. Over-reliance on a
single drive — typically Black Hat Loss Aversion (streaks, countdown
timers) — gets rebalanced toward White Hat drives.

Retention curves flatten at higher levels as motivation architecture
deepens across phases. Endgame users — who often disengage in thin
gamification systems — stay longer because mastery identity and
legacy drives sustain them past the novelty phase. The team stops
shipping one-off badges and starts shipping motivation architecture.

## Quality Gates

- Current product mapped against all 8 drives with gaps and
  over-reliance explicitly noted.
- Drive-by-phase mapping exists for all 4 lifecycle phases
  (discovery, onboarding, scaffolding, endgame).
- White Hat / Black Hat balance is deliberately set, with Black Hat
  drives constrained to specific moments rather than dominant.
- Over-justification risk is assessed before gamifying any
  intrinsically motivated workflow.
- Quarterly re-audit cadence is scheduled.

## Companion Integration

Complements `matilha-ux-pack:ux-intrinsic-motivation` which applies SDT (autonomy/competence/relatedness) at feature level. This skill operates at gamification system architecture level across an entire product.

Invoked by Matilha core skills (`matilha-plan`) when motivation
architecture decisions span multiple lifecycle phases. Pairs with
`growth-hook-model-product` (Hook Model at product-flow level;
Octalysis at drive-architecture level — complementary at different
abstractions) and with `growth-peak-end-journey` (peaks and endings
are the moments where drives land most strongly).

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: full 8-drive map against current product;
  drive-by-phase mapping across 4 lifecycle phases; White Hat
  dominance in overall balance.
- Use "should" for: quarterly re-audit cadence; phased shipping
  rather than all-at-once.
- Use "may" for: the specific UI surfaces chosen for each drive —
  product-dependent.

## Troubleshooting

- **"Engagement spikes then collapses"**: Typically Black Hat
  dominance (Scarcity/Loss). Rebalance toward White Hat drives.
- **"Gamification feels tacked on"**: The drives are on a separate
  layer (rewards tab, profile badges) rather than woven into core
  product activity. Integrate into the workflows users already take.
- **"Veterans disengage"**: Endgame drives are thin. Add mastery
  identity, legacy, community-mentorship roles. Early drives
  (Development, Empowerment) fade as competence rises.
- **"We added a drive and intrinsic motivation dropped"**: Over-
  justification effect. The activity was already intrinsically
  motivated; extrinsic layering erodes it. Remove the added layer.

## Concrete Example

Duolingo is a mature example. Epic Meaning ("bilingualism is a
life-changing skill"). Development & Accomplishment (XP, levels,
skill trees). Empowerment of Creativity (speech-recording exercises,
sentence construction). Ownership & Possession (lingots, streak
count). Social Influence (leagues, friend activity). Scarcity &
Impatience (limited hearts). Unpredictability & Curiosity (chest
rewards, surprise streak bonuses). Loss & Avoidance (streak freeze,
loss aversion messaging). All 8 drives active, woven into core
practice activity, balanced across lifecycle phases. Contrast: a
B2B SaaS bolts on a "earn points by logging in" layer. Weak —
disconnected from core activity, leans on Black Hat Scarcity only,
ignores the other 7 drives. Drops meaning within weeks as users
discover the points lead nowhere.

## Sources

- `[[concepts/frameworks-comportamentais]]`
- `[[sources/product-htrategy]]`
- Inspired by Yu-kai Chou's "Actionable Gamification: Beyond Points,
  Badges, and Leaderboards" and his Octalysis framework (including
  Level 2 experience phases), paraphrased through Danilo's wiki
  synthesis of Octalysis as a multi-drive architecture across
  lifecycle rather than a points-and-badges layer.
