---
name: growth-north-star-metric
description: Use when picking or aligning the single business metric — identify the North Star that captures sustainable value delivered to users.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team has too many dashboards, too many targets, and no agreement
on which number matters most. Fires when leadership asks "how are we doing?"
and gets a different answer from each function. The skill picks one metric
that best captures the value users actually receive, ties downstream KPIs
to it, and lets the organization stop negotiating goals and start
optimizing one signal.

## Preconditions

- The product has at least one concrete value moment — something a user
  does that corresponds to a real benefit, not just activity.
- There is willingness to deprecate secondary "company metrics" that
  currently compete with the proposed North Star.
- Someone can name the user segment whose value this metric is meant to
  capture; a North Star without a segment drifts toward vanity.

## Execution Workflow

1. Use Read on product, strategy, and customer-success documents to list
   every metric the organization currently tracks as "important." Expect
   somewhere between eight and thirty.
2. Classify each metric into one of three buckets. Input metrics are things
   the company does (ads run, emails sent, features shipped). Output metrics
   are lagging results (revenue, headcount, retention rate). Value metrics
   describe what the user experiences when the product works (projects
   completed, nights booked, messages delivered). North Star candidates
   live only in the third bucket.
3. For each value-metric candidate, ask three questions. Does it move when
   the product genuinely improves for the user? Does it correlate with
   long-term retention and revenue at a lag of weeks or months? Can the
   whole organization act on it — product, engineering, marketing, support?
   A candidate that fails any of the three is not a North Star.
4. Pick the candidate that best fits the product's business model. A
   marketplace cares about matched transactions. A content product cares
   about consumed minutes or sessions. A collaboration tool cares about
   team-shaped activity, not individual action. Match the metric to the
   model.
5. Write the metric as a sentence. Not "DAU" but "daily users who performed
   the core value action." Not "revenue" but "weekly revenue from retained
   customers." The sentence form forces precision and catches proxies
   masquerading as North Stars.
6. Decompose it into a growth equation. Airbnb's nights booked breaks into
   new-host onboarding times listing quality times search-to-book
   conversion times repeat rate. The decomposition gives each team a lever
   and shows how their work rolls up.
7. Use TodoWrite or a short memo to propose the change. Flag which existing
   targets get demoted or retired. Changing the North Star is a strategic
   signal; name the shift explicitly.

## Rules: Do

- Pick a metric that moves only when users receive real value, not when the
  company pushes harder.
- Express the North Star as a sentence that names the user, the action, and
  the window (weekly, monthly, per-session).
- Decompose the North Star into an equation so every team sees their
  contribution.
- Demote or retire metrics that compete for attention once the North Star
  lands; two North Stars is the same as none.
- Revisit the choice when strategy pivots — the North Star is stable across
  tactics but responsive to genuine strategic change.

## Rules: Don't

- Don't pick raw revenue as North Star — it lags the value delivery by
  months and is pushable through pricing tricks that harm users.
- Don't pick sign-ups or DAU without tying them to a value moment; both
  are easy to inflate without improving the product.
- Don't pick a metric only product can move; North Stars must be
  cross-functional levers.
- Don't average different user segments into one metric when their value
  moments differ substantially.
- Don't change the North Star for tactical reasons — the cost of
  re-aligning the organization is high.

## Expected Behavior

After applying the skill, a team's weekly review compresses. One chart
anchors the conversation. Side metrics appear only to explain movement in
the North Star, not to compete with it. Feature pitches start citing how
they move the North Star equation rather than ad-hoc proxies, and
proposals that do not plug into the equation face a sharper filter.

Leadership stops asking "what should we focus on this quarter?" because
the answer is structurally derived from which term of the growth equation
is lagging. The metric also gives new hires and cross-functional partners
a fast way to understand what the company believes value looks like.

## Quality Gates

- The North Star is written as a full sentence, not an acronym or a
  one-word label.
- It decomposes into at least three multiplicative terms that map to
  different functions.
- Every existing "top-line" metric has either been subsumed by the North
  Star decomposition or explicitly demoted.
- The metric changes when user experience changes, not when marketing
  volume changes.
- The time window (daily, weekly, monthly) is specified and defensible.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
strategy or alignment questions surface. Often pairs with
`growth-aarrr-funnel` (the North Star sits above AARRR and guides which
stage matters most) and with `growth-instrumentation-plan` (the events you
instrument should feed the growth equation). Does not delegate to other
packs in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: tying the metric to a user-side value action, writing it
  as a sentence.
- Use "should" for: decomposing into a growth equation, retiring competing
  metrics.
- Use "may" for: the specific time window and which segment of users the
  metric counts, adjusted to the product model.

## Troubleshooting

- **"We can't get alignment — every team wants a different metric"**: That
  is the symptom that precedes this skill. Run the classification step in
  a single room; inputs and outputs will fall away and value candidates
  will surface quickly.
- **"Our North Star went up but revenue fell"**: Check the correlation
  assumption. If short-term North Star growth does not predict long-term
  revenue, the metric is likely an input or vanity measure disguised as
  value.
- **"The team is gaming the North Star"**: Gaming is a sign the metric
  captures the action, not the underlying value. Tighten the definition —
  add quality criteria, minimum session length, or outcome confirmation.
- **"We have two North Stars — one for growth, one for revenue"**: Two
  North Stars is the same as none. Pick the one closer to user value;
  revenue will follow at a lag if the choice is right.

## Concrete Example

A project-management SaaS lists "paying users" as its company-level
metric. The team optimizes accordingly: pricing experiments, upsell
popups, billing-cycle nudges. Six months in, churn has risen, support
tickets have risen, and growth has stalled. The reading surfaces that
paying users is an output metric — it lags product value and rewards
tactics that harm the user relationship. The team shifts to "projects
completed per team per week." The new equation pulls in team size,
activation quality, collaboration depth, and retained-team rate. Product
starts shipping work on team onboarding and collaboration polish,
marketing targets the buyer segments whose teams actually collaborate,
and within two quarters the original revenue metric recovers — as a
consequence of the shift, not as its target.

## Sources

- `[[sources/product-growth-hacking]]`
- `[[sources/product-htrategy]]`
- `[[concepts/aarrr-growth-metrics]]`
- Inspired by Sean Ellis's 2017 formulation of the North Star Metric,
  paraphrased further through Danilo's wiki synthesis of the Airbnb,
  Spotify, and Shopify growth-equation examples.
