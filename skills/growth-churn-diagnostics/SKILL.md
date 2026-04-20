---
name: growth-churn-diagnostics
description: Use when investigating churn — classify voluntary vs involuntary churn and diagnose root cause by cohort stage.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when leadership sees a rising or stubborn churn number and asks
the team to fix it, without a shared view of what kind of churn is
happening or at what stage of the customer lifecycle it occurs.
Fires when the monthly churn figure is reported as a single
percentage that rolls payment failures, early-stage disengagement,
and late-stage attrition together into one indistinct mass. The
skill decomposes the number into its real components — voluntary
versus involuntary, early versus mid versus late — and routes each
component to the intervention it actually needs.

## Preconditions

- Billing data is accessible and can be cross-referenced with
  cancellation events, so the voluntary-involuntary split is
  observable.
- Cancellation events carry at least a timestamp and a cohort
  anchor, so the stage of the lifecycle at churn is visible.
- Exit-survey or behavioral-signal data exists, even if noisy, so
  voluntary churn can be partially attributed.

## Execution Workflow

1. Split churn into voluntary and involuntary. Involuntary churn is
   payment failure, expired cards, and disputes — the customer did
   not choose to leave but the system classified them as gone.
   Voluntary churn is the customer clicking cancel or letting a
   contract lapse. In many SaaS products, involuntary is twenty to
   forty percent of total churn and hides in the aggregate.
2. Fix involuntary churn first. It has the best return per unit of
   effort. The intervention stack is well-known: pre-expiration
   reminders, dunning email sequences, intelligent retry logic for
   failed payments, multiple payment method support, and grace
   periods before cancellation. Each step converts some fraction of
   involuntary into retained revenue.
3. For voluntary churn, bucket by cohort stage. Early churn (within
   the first thirty days) usually signals activation failure —
   the user never reached value. Mid churn (months two through
   four) usually signals habit failure — the user reached value
   once but did not embed the product in a recurring workflow.
   Late churn (month five and beyond) usually signals a market
   shift — competitor, priority change, strategic realignment on
   the customer side.
4. Run diagnosis per stage. For early churn, review onboarding
   telemetry and the first-session journey — which step lost them.
   For mid churn, review engagement patterns — did they log in and
   then stop, or did they never come back after a single success.
   For late churn, interview — behavioral signals are weaker here
   and customer context matters more.
5. Design stage-specific interventions. Early churn is an onboarding
   redesign, not an email campaign. Mid churn is a habit-formation
   intervention — reminders, integrations, recurring value pings.
   Late churn is a relationship intervention — account management,
   renewal conversations, expansion plays.
6. Distinguish churn rate from revenue churn. A customer who
   downgrades from the target tier to entry is not counted as
   logo churn but represents revenue churn. Track both and do not
   confuse them in decks.
7. Use TodoWrite to capture the voluntary-involuntary split, the
   cohort-stage breakdown, the diagnosis per stage, and the
   intervention owner. Churn work fragments fast without
   ownership.
8. Re-measure after each intervention lands. Churn is noisy at
   small volumes; do not over-interpret a single month.

## Rules: Do

- Split churn into voluntary and involuntary before any other
  analysis; the two have entirely different interventions.
- Fix involuntary churn first — it is the lowest hanging fruit in
  almost every SaaS.
- Bucket voluntary churn by lifecycle stage (early, mid, late);
  each stage needs a different intervention.
- Track revenue churn separately from logo churn; downgrades hide
  in aggregate.
- Use exit surveys as one signal among several; correlate with
  behavioral data before trusting them.

## Rules: Don't

- Don't report a single monthly churn number without the split; it
  is almost always misleading.
- Don't run blanket win-back campaigns across all churned users;
  different stages need different language, and spraying dilutes
  the message.
- Don't treat exit-survey free-text as the final word. Users
  explain their cancellation in the frame that feels least
  confrontational, not the most accurate one.
- Don't remove the cancel flow's honesty; a cancel path that is
  hard to find or requires a phone call trades a short-term
  retention bump for a long-term trust collapse.
- Don't confuse churn rate with NRR. Net revenue retention bakes
  in expansion; churn rate does not; strategic conclusions
  diverge on which metric you read.

## Expected Behavior

After the skill, the churn conversation changes shape. Instead of
"churn is eight percent," the team says "involuntary is two
percent, early voluntary is two-point-four, mid voluntary is
two-point-four, late voluntary is one-point-two" and can point at
four different workstreams with four different owners. The
aggregate number still matters, but decisions happen on the
components.

Over a quarter, interventions land on specific buckets and move
specific numbers. The team develops a diagnostic reflex: every time
churn moves, they first check which component moved. Win-back
campaigns become targeted rather than blanket, and cancellation UX
becomes a place where honest signal is captured, not where the
company tries to guilt users into staying.

## Quality Gates

- Churn is reported with the voluntary-involuntary split, not as a
  single aggregate.
- Voluntary churn is bucketed by cohort stage (early, mid, late),
  each with its own intervention owner.
- Involuntary churn has a dunning and retry system in place, not
  just a single failed-payment email.
- Revenue churn is tracked separately from logo churn, and
  downgrades are visible.
- Cancellation UX captures honest signal — exit survey, reason,
  optional free text — without dark patterns in the flow.

## Companion Integration

Invoked by Matilha core skills when retention and revenue appear in
the same breath. Pairs tightly with `growth-retention-curves` (the
curve shape points at which cohort-stage drives churn) and with
`growth-activation-aha-moment` (activation failure is the usual
root cause of early voluntary churn). Downstream of
`growth-value-metric` — a misaligned value metric often shows up as
mid-stage voluntary churn.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: voluntary-involuntary split, cohort-stage
  bucketing of voluntary churn, separate tracking of revenue
  churn.
- Use "should" for: dunning and retry logic for involuntary churn,
  onboarding review for early voluntary churn, habit intervention
  for mid voluntary churn.
- Use "may" for: the specific exit-survey questions, the specific
  retry cadence, the specific win-back incentives, which are
  product-specific.

## Troubleshooting

- **"Exit surveys say 'too expensive' across the board"**: Price is
  the socially-acceptable reason; it is rarely the real one.
  Cross-reference exit-survey text with engagement data. Users who
  never used the product blame price; users who churn with high
  engagement almost never do.
- **"Involuntary churn is low and we have no dunning to speak of"**:
  Possibly — or involuntary churn is being miscounted as voluntary
  because the cancel happens when the card expires. Audit the
  billing pipeline.
- **"Mid-stage churn keeps coming back"**: Habit did not form.
  Either the product's recurring value pings are too weak or the
  integration surface is too shallow. Look at which mid-stage
  users retained and what they did differently.
- **"Late-stage churn is rising"**: Competitor, market shift, or a
  silent feature regression. Interview late-stage churners
  individually; behavioral signals are weak at this stage and
  qualitative matters more.

## Concrete Example

A SaaS sees monthly churn at eight percent. After the split: two
percent involuntary, six percent voluntary. Of the voluntary, forty
percent cancel in month one (activation failure), forty percent in
months two through four (habit failure), and twenty percent in
month five or later (late-stage competitive loss). The team runs
three parallel interventions. Dunning and card-retry logic ship for
the involuntary two percent, reclaiming about thirty percent of it.
An onboarding redesign targets the early forty-percent bucket,
cutting early churn roughly in half. An engagement intervention —
weekly digest emails with personalized value summaries — targets
the mid bucket, with modest but real effect. Four months later,
aggregate monthly churn sits at four-point-five percent, and the
team can explain why number by number.

## Sources

- `[[sources/product-growth-hacking]]`
- `[[concepts/aarrr-growth-metrics]]`
- `[[concepts/plg-estrategias-growth]]`
- Inspired by Patrick Campbell's churn decomposition at ProfitWell
  and the retention-diagnostic chapters of the Product Growth
  Hacking source, paraphrased through Danilo's wiki synthesis of
  cohort-stage attribution and dunning design.
