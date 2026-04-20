---
name: growth-fogg-bmap-feasibility
description: Use when evaluating behavior-change feasibility — apply Fogg Behavior Model (B=MAP) to validate whether a feature can drive the desired behavior.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team is deciding whether a proposed feature can realistically
drive the behavior it is meant to cause. Fires when retention,
activation, or conversion targets are missed and the team is about to
blame motivation ("users don't care enough") — often the real
bottleneck is ability or prompt, which are cheaper to fix. This skill
is foundational diagnostic, applied before design investment, to
prevent shipping features that mis-diagnose the bottleneck.

## Preconditions

- The target behavior can be named precisely — not "engagement" but
  "start a second workout within 7 days of completing the first." Fog-
  gy behavior definitions produce foggy B=MAP analyses.
- The team has access to some behavioral data, even if thin — funnel
  drop-off, session duration, feature usage. Pure-opinion B=MAP
  analysis drifts toward blame-motivation conclusions by default.
- Leadership accepts that "users don't want it enough" is often wrong.
  Motivation is the most expensive factor to move; ability and prompt
  are usually the real bottleneck.

## Execution Workflow

1. Use Read on funnel data and behavioral instrumentation. Identify
   the one specific behavior the proposed feature is meant to drive.
   If the team cannot write it as one sentence with a subject, verb,
   object, and timing, the behavior is not specified enough.
2. Score Motivation. Ask: why does the user care, right now, to do
   this? Pain, aspiration, social pressure, fear of loss. Rate
   high/medium/low with evidence from user interviews or behavioral
   proxies (repeat visits, support-ticket volume).
3. Score Ability. Walk through the 6 simplicity factors: time
   required, money cost, physical effort, mental effort, social
   deviance (does the user have to act against group norms?), routine
   disruption (does it break an existing workflow?). The weakest
   factor dominates — all 6 must be tolerable or ability is low.
4. Score Prompt. Is there a trigger that fires at the moment
   motivation and ability converge? Internal (emotional cue, context)
   or external (notification, UI affordance, email). A missing prompt
   is the cheapest bottleneck to fix and the most commonly misdiagnosed
   one.
5. Identify the zero. B=MAP is multiplicative — if any factor is zero,
   behavior does not happen regardless of the other two. Most
   behavior-change failures trace to one factor near zero, not all
   three being lukewarm.
6. Optimize in cost order. Prompt is cheapest to add or move; ability
   is mid-cost (UI changes, friction reduction); motivation is most
   expensive (narrative, positioning, pricing changes). Start cheap,
   verify, then escalate.
7. Distinguish from Hook Model work. Fogg is single-behavior
   feasibility ("can this one behavior happen?"). Hook is habit-loop
   architecture over many cycles. Do not conflate them. Use
   `growth-hook-model-product` when the question is "should this
   behavior repeat and form a habit," not "can it happen once."
8. Ship a minimum feasibility patch. Before a major redesign, test
   the cheapest bottleneck fix (usually prompt). If it moves the
   metric, the diagnosis holds; if not, re-score ability and only
   then motivation.

## Rules: Do

- Name the target behavior precisely — subject, verb, object, timing
  — before scoring B=MAP.
- Score all 3 factors with evidence, not intuition. "Users seem
  motivated" is not a score; repeat visits and support tickets are.
- Identify the zero first. B=MAP is multiplicative; one near-zero
  factor is the bottleneck.
- Optimize in cost order: prompt first, ability second, motivation
  last. Prompt fixes are often single-line changes.
- Walk through all 6 simplicity factors for ability. The weakest
  factor dominates, and it is often not the obvious one.

## Rules: Don't

- Don't blame motivation by default. "Users aren't motivated" is the
  lazy diagnosis and usually wrong. Score ability and prompt first.
- Don't treat B=MAP as additive. Two strong factors do not compensate
  for one zero factor; behavior still does not happen.
- Don't confuse B=MAP with habit architecture. Fogg checks whether
  one behavior can happen; Hook checks whether it repeats into a
  habit. Different skills, different questions.
- Don't skip the precise-behavior definition. Foggy behavior
  ("engagement," "activation," "stickiness") produces foggy diagnosis.
- Don't ship a redesign before testing the cheapest hypothesis first.
  Prompt fixes are frequently sufficient.

## Expected Behavior

After applying the skill, the team stops defaulting to "users aren't
motivated enough" and starts asking "is ability the bottleneck, or
prompt?" Cheap prompt fixes (moving a notification timing, surfacing
a CTA at the right step) move metrics that the team previously
assumed required a big redesign. When ability is the bottleneck, the
team walks through the 6 simplicity factors and finds the specific
one holding the behavior back — often mental effort or routine
disruption, not time or money.

Over time, feature-decision conversations include a B=MAP score
before design work starts. Features that score near-zero on any
factor get re-scoped or killed before they consume design and
engineering cycles. The team's feature-to-impact ratio improves
because fewer features ship with pre-built ability or prompt
bottlenecks.

## Quality Gates

- Target behavior is named precisely (subject, verb, object, timing).
- All 3 factors (Motivation, Ability, Prompt) are scored with
  evidence, not intuition.
- The "zero" factor (if any) is identified, and the proposed fix
  targets it rather than the wrong factor.
- The cheapest hypothesis (usually prompt) is tested before
  higher-cost redesigns are committed.
- The analysis distinguishes B=MAP (single-behavior feasibility) from
  Hook Model (habit-loop architecture) — the two are not merged.

## Companion Integration

No direct `matilha-ux-pack` sibling; this skill is foundational. Used
strategically to gate feature decisions before UX skills design the
execution.

Invoked by Matilha core skills (`matilha-plan`) before feature design
begins and by `matilha-scout` when retention or conversion metrics
are under diagnosis. Pairs with `growth-hook-model-product` (use
B=MAP for single-behavior feasibility, Hook for habit-loop
architecture) and with `growth-activation-aha-moment` (activation
failures frequently trace to low ability or missing prompt).

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: precise behavior definition; evidence-backed
  scoring of all 3 factors; identification of the zero factor.
- Use "should" for: cost-ordered optimization (prompt first, ability
  second, motivation last); cheap hypothesis test before big
  redesign.
- Use "may" for: the specific simplicity factor prioritized within
  ability (time vs mental effort vs routine disruption) —
  context-dependent.

## Troubleshooting

- **"We improved motivation but behavior didn't happen"**: Motivation
  was not the bottleneck. Re-score ability and prompt; the zero
  factor is elsewhere.
- **"Users say they want it but don't do it"**: Classic ability or
  prompt gap. Stated motivation is real; the behavior is not
  happening because ability is low or no prompt fires at the right
  moment.
- **"Prompt is fine, ability is fine, but metric doesn't move"**: The
  precise behavior definition may be wrong. The team may be measuring
  a proxy that does not actually reflect the target behavior.
- **"The 6 simplicity factors all look okay"**: One is not okay. The
  weakest factor dominates; go back and stress-test each one against
  real user workflows, not self-reports.

## Concrete Example

A meditation app launches. Install rate is high but Day-7 retention
is low. The team's first instinct is "users aren't motivated enough —
let's add a motivation campaign." B=MAP diagnosis: Motivation is
actually high (users self-identify wanting calm, repeat installs
confirm). Prompt is fine (daily notification arrives on time).
Ability is LOW — sessions require 15 minutes in a quiet room, and
users cannot find 15 free minutes reliably. Time and routine
disruption are both weak. The team ships a 3-minute micro-meditation
mode. Ability rises sharply, the behavior happens, Day-7 retention
climbs within two weeks. A motivation campaign was unnecessary and
would have wasted the quarter.

## Sources

- `[[concepts/frameworks-comportamentais]]`
- `[[sources/product-htrategy]]`
- Inspired by BJ Fogg's "Tiny Habits" and his Behavior Design Lab
  research at Stanford, paraphrased through Danilo's wiki synthesis
  of B=MAP as a feasibility diagnostic applied before design rather
  than as a retrospective post-mortem tool.
