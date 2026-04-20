---
name: growth-aarrr-funnel
description: Use when analyzing acquisition and retention as a funnel — apply AARRR (Pirate Metrics) stage-by-stage from acquisition through revenue.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a product team is trying to figure out why growth is stuck, where
spend is leaking, or how to sequence investment across acquisition, onboarding,
retention, referral, and monetization work. Fires when someone frames a
problem as "we need more users" without first asking whether the users they
have stay. The skill diagnoses each AARRR stage in turn and names the single
bottleneck that is capping everything downstream.

## Preconditions

- A product already has some user traffic or sign-ups; AARRR is diagnostic,
  not a zero-to-one blueprint.
- Raw counts exist for at least acquisition volume and some weekly-active or
  retained-user measure — even rough numbers are enough to start.
- The team can name the product's core value moment or is willing to define
  one before stage analysis begins.

## Execution Workflow

1. Use Read or the analytics tool of record to pull the last 30 to 90 days of
   counts for five stages: new visitors or trial starts (Acquisition),
   first-value actions (Activation), repeat actions within a cohort window
   (Retention), upgrades or paid events (Revenue), and invites-sent and
   invites-accepted (Referral). Write them down as a vertical column.
2. Compute conversion rates between neighboring stages. These rates, not the
   absolute counts, tell the story. A sign-up to activation rate under roughly
   twenty percent is a red flag. A D7 retention under ten percent is another.
   A K-factor under 0.2 means referrals are doing nothing for growth.
3. Identify the single weakest rate. The weakest stage is the bottleneck —
   every dollar spent upstream of it is partially wasted until it is fixed.
   Do not try to improve every stage in parallel; pick one.
4. Match the bottleneck to the right kind of intervention. Acquisition leaks
   point at channel-product fit or landing-page copy. Activation leaks point
   at first-value time and onboarding friction. Retention leaks point at
   product value or habit formation. Revenue leaks point at pricing or upgrade
   triggers. Referral leaks point at loop design or invite incentive.
5. Use TodoWrite or a lightweight plan to propose two or three concrete
   experiments for the chosen stage, scored roughly by impact and ease. Do not
   promise improvements to the other stages in the same iteration.
6. Re-measure after two to four weeks, using the same cohort definitions.
   Moving the weakest stage by even a few percentage points often unlocks more
   downstream revenue than doubling the strongest stage.
7. Know when AARRR is the wrong frame. Some products need an added Awareness
   stage upstream (when nobody has heard of the category). Some mature SaaS
   products are better served by a retention-first reading where existing
   users are the growth engine and the order starts with Retention. The
   framework is a lens, not a prescription.

## Rules: Do

- Diagnose by rate between stages, not by absolute counts at any single stage.
- Fix the weakest stage before spending more on the stage just upstream of it.
- Separate Acquisition-stage problems (wrong people arriving) from
  Activation-stage problems (right people, wrong first experience) — they
  feel similar in dashboards but have different fixes.
- Define a concrete first-value action for Activation before measuring it.
  Without a named action, Activation becomes indistinguishable from sign-up.
- Re-cut numbers by cohort when comparing; absolute rates without a cohort
  window almost always mislead.

## Rules: Don't

- Don't spend on paid Acquisition when Retention is broken — the spend
  multiplies the leak instead of the growth.
- Don't treat sign-up as activation; sign-up is an input, activation is the
  first moment the user experiences value.
- Don't average metrics across months that span product changes; that washes
  out the signal the change was supposed to produce.
- Don't report AARRR stages without defining what each event means for this
  product — McClure's labels are not self-interpreting.
- Don't declare victory because one stage improved; check that downstream
  stages did not regress.

## Expected Behavior

After applying the skill, the team stops arguing about whether to "do
marketing" or "fix the product" and instead points at a single rate on a
single line of the funnel. Follow-up decisions get cheap: the product team
knows what to ship next, the growth team knows what to test, and the finance
team understands why a previously-planned ad spend is being deferred until
the activation work lands.

Over time, AARRR becomes the shared vocabulary of the review meeting. A
feature pitch that cannot name which stage it moves is sent back for
sharpening. Experiments that move the weakest stage get greenlit even when
they look modest; experiments that move an already-strong stage get
deprioritized even when they look flashy.

## Quality Gates

- Every stage has a named event or metric specific to this product, not a
  generic label.
- The weakest stage is explicitly identified before any fix is proposed.
- Each proposed experiment is tied to exactly one stage and has a target
  delta expressed in percentage points.
- Downstream stages are re-measured after an upstream fix to catch
  unintended regressions.
- The team can explain in one sentence why they are investing in stage X
  rather than stage Y this cycle.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when product
and business decisions surface growth questions. Often runs before
`growth-instrumentation-plan` (you need to know which stages matter before
instrumenting them) and before `growth-activation-aha-moment` (AARRR often
surfaces Activation as the bottleneck that triggers aha-moment work). Does
not delegate to other packs in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: identifying the weakest stage before proposing fixes,
  defining product-specific events for each stage.
- Use "should" for: cohort-cut metrics, experiment scoping to a single
  stage.
- Use "may" for: whether to add an Awareness stage upstream or reorder into
  retention-first, depending on product maturity.

## Troubleshooting

- **"All five stages look weak"**: This is usually a measurement artifact,
  not reality. Re-check that Activation is defined as first-value (not
  sign-up) and that Retention uses a cohort window, not a snapshot. Two
  stages will almost always separate once definitions tighten.
- **"We fixed Activation but revenue didn't move"**: Revenue is downstream
  of Retention, not Activation. A bigger activation pool with the same
  retention curve produces the same paid pool at a lag. Wait at least one
  retention cycle before judging the revenue effect.
- **"The K-factor looks great but users aren't growing"**: Check cycle
  time. A K of 0.8 with a 90-day cycle loses to a K of 0.3 with a 7-day
  cycle over the course of a quarter.
- **"Leadership wants to run ads now"**: If Activation or Retention is below
  benchmark, put the paid number through a leak calculator and show the
  dollar cost of acquiring users who will not retain. The number usually
  ends the conversation.

## Concrete Example

A mid-stage SaaS runs at twenty percent activation (sign-up to first project
created) and fifty percent D7 retention among activated users. Leadership
proposes a six-figure ad campaign to double sign-ups. The AARRR reading
surfaces the real shape: eighty percent of sign-ups never reach first value,
so doubling sign-ups doubles the wasted cost without moving the retained
user base by more than a few percent. The recommendation instead is to
spend a quarter fixing Activation — adding a sample-data empty state, a
guided first-project flow, and a day-two nudge email. When Activation rises
to thirty-five percent, the same ad dollars now move the retained base
proportionally, and the finance case for the campaign actually holds.

## Sources

- `[[concepts/aarrr-growth-metrics]]`
- `[[sources/product-growth-hacking]]`
- Inspired by Dave McClure's 2007 "Startup Metrics for Pirates" talk,
  paraphrased further through Danilo's wiki synthesis of SaaS benchmarks
  and the leaky-bucket principle.
