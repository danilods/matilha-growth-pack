---
name: growth-retention-curves
description: Use when analyzing retention health — apply D1/D7/D30 cohort curves to diagnose smile vs flat vs decay retention shapes.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when the team wants to know whether the product retains users,
but the only number on the dashboard is a single monthly retention
percentage with no cohort structure behind it. Fires when a leader
asks "is retention good?" and the answer depends on when the user
signed up, which acquisition channel brought them, and which
onboarding variant they saw — none of which an aggregate number
reveals. The skill forces the team to draw retention as curves, not
as a single number, and to read the curve's shape rather than its
headline value.

## Preconditions

- Users can be bucketed into cohorts by a meaningful event — signup
  date, first activation, trial start — with a tracked identifier
  that persists across sessions.
- There is enough usage history to draw curves with at least thirty
  days of post-cohort data; shorter windows give misleading shapes.
- The team can decide on a single "active" definition per cohort,
  tight enough to be meaningful (not just "logged in") but loose
  enough to include real use (not just a single power-user feature).

## Execution Workflow

1. Pick the cohort anchor. Signup is tempting but weak — users who
   never activated never had a retention story. Prefer the first
   activation event (first task completed, first invite sent, first
   document created) when the product has one.
2. Pick the "active" definition. The definition should tie to the
   product's natural cadence: daily for social tools, weekly for work
   tools, monthly for utilities. A too-strict definition makes every
   product look like it has decay retention; a too-loose one hides
   real churn.
3. Pick the D-intervals. D1 plus D7 captures early drop for daily
   products; D7 plus D30 suits weekly products; D30 plus D90 fits
   monthly utilities. Report two intervals so the curve's shape is
   visible, not just a single point.
4. Draw the curve per cohort. Plot percent of cohort still active at
   each interval. Compare cohorts by acquisition channel, onboarding
   variant, plan tier, or any dimension that might segment
   experience.
5. Classify the shape. Smile retention drops sharply then climbs as
   surviving users return more often — a rare and strong PMF signal.
   Flat retention shows a stable retained subset after early churn —
   the common, healthy pattern if the retained subset is large enough
   to sustain growth. Decay retention drops steadily toward zero —
   the failure shape, indicating no durable user segment.
6. Segment. Segment cohort curves by channel, onboarding variant,
   plan tier, and any signal that matters. A single aggregate curve
   hides more than it reveals; the per-segment curves point at the
   intervention.
7. Ship the intervention against the weakest segment first. If cohort
   A retains well and cohort B retains poorly, shifting cohort A's
   experience onto cohort B is usually the highest-leverage move.
8. Use TodoWrite to log the cohort definition, the active definition,
   the D-intervals, the per-segment curves, and the intervention
   hypothesis. Retention work without logs repeats the same
   investigation every quarter.

## Rules: Do

- Measure retention from activation, not signup, whenever activation
  has a clear definition.
- Draw retention as curves, not as a single percent; the shape is
  the signal.
- Segment by acquisition channel, onboarding variant, and plan tier
  at minimum; hidden heterogeneity is the usual story.
- Match the D-interval to the product's natural cadence.
- Treat a stable flat plateau as a real PMF signal even if the
  absolute percent looks modest.

## Rules: Don't

- Don't report monthly "retention" as a single number without a
  cohort structure; the number is almost always misleading.
- Don't define "active" as "logged in" — the definition must tie to
  value delivered, or the curve measures nothing real.
- Don't compare cohorts across definition changes; if the active
  definition changes, the old and new curves are not the same
  quantity.
- Don't chase smile retention as a goal; it is a happy outcome, not
  a target, and most healthy products are flat, not smile.
- Don't ignore the long tail. A cohort stabilizing at fifteen percent
  after month three is a durable fifteen percent that can support a
  real business if acquisition volume is high enough.

## Expected Behavior

After the skill, the team reads retention as a shape per cohort per
segment rather than as a single percent on a slide. Conversations
shift from "retention is bad" to "cohort B retains flat at fifteen
percent, cohort A at thirty, so the onboarding variant B saw is the
problem." Interventions target specific cohorts and get measured on
those specific curves, which shortens feedback loops and sharpens
decisions.

Over quarters, the retention curve becomes a living artifact. The
team knows the shape in its sleep, argues about deviations from it,
and catches regressions within weeks instead of months. Retention
becomes a moat metric — not the acquisition funnel's afterthought.

## Quality Gates

- Cohorts are anchored on a clear activation event, not just signup.
- The "active" definition is documented and stable over the
  reporting period.
- At least two D-intervals are reported per cohort, so curve shape is
  visible.
- Cohorts are segmented by at least two dimensions (typically channel
  and onboarding variant).
- The team can name the curve shape (smile, flat, decay) for the
  current primary cohort in one sentence.

## Companion Integration

Invoked by Matilha core skills when retention shows up in a roadmap
discussion. Pairs with `growth-churn-diagnostics` (diagnostics
explain the drop visible in the curve) and with
`growth-activation-aha-moment` (activation quality directly shapes
the D1 and D7 reads). Upstream of `growth-north-star-metric` — a
healthy retention curve is a necessary condition for a meaningful
NSM.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: activation-anchored cohorts where activation is
  defined, curves rather than single percents, at least two
  D-intervals.
- Use "should" for: segmentation by channel and onboarding variant,
  match between D-interval and product cadence.
- Use "may" for: the specific active definition and the absolute
  threshold that counts as "healthy," which are product-specific.

## Troubleshooting

- **"All cohorts look like decay"**: The active definition is likely
  too strict, or cohorts are signup-anchored rather than
  activation-anchored. Loosen the definition or anchor at
  activation.
- **"All cohorts look flat and fine"**: The active definition is
  probably too loose ("opened the app"). Tighten it to something
  that represents value delivered.
- **"Curves disagree wildly by channel"**: This is a feature, not a
  bug — channels attract different intent. Concentrate acquisition
  on the channel whose cohorts retain best.
- **"Curve shape flipped last quarter"**: Something upstream
  changed. Suspects: onboarding variant rollout, acquisition mix
  shift, active definition change, product regression. Bisect by
  cohort.

## Concrete Example

A fitness SaaS measures retention as a single monthly number — "we
retain about twenty-eight percent." Leadership is unsatisfied but
has no next step. The team anchors cohorts on first-workout
completion, defines "active" as at least one workout per week, and
draws D7, D30, and D90 curves per onboarding variant. The aggregate
twenty-eight-percent turns out to hide two radically different
stories: onboarding variant A retains flat at eighteen percent,
variant B retains flat at thirty-four percent. The team routes all
signups to variant B. Three months later, the aggregate retention
rises to thirty-four percent — a thirty-six percent improvement in
long-term cohort LTV — without any change to acquisition cost.

## Sources

- `[[concepts/aarrr-growth-metrics]]`
- `[[sources/product-growth-hacking]]`
- `[[concepts/plg-estrategias-growth]]`
- Inspired by Sequoia's retention-curve teaching (Jamie Quint,
  Andrew Chen) and the cohort-analysis chapters of the Product
  Growth Hacking source, paraphrased through Danilo's wiki
  synthesis of activation-anchored cohorts and segmentation cadence.
