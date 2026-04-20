---
name: growth-freemium-strategy
description: Use when designing freemium conversion — define free-to-paid thresholds that showcase value without cannibalizing paid tier, using ethical friction.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team is debating whether to offer a free tier, or when an
existing free tier is either cannibalizing paid revenue or failing to
bring in new users at all. Fires when the pricing page carries a
"Free" entry and nobody on the team can answer cleanly what the free
tier exists to do, or where the upgrade trigger is supposed to land in
a customer's lifecycle. The skill separates freemium from trial,
names the boundary that turns free users into paid users, and builds
that boundary to fire at a moment of natural growth rather than
arbitrary friction.

## Preconditions

- The product delivers value in a standalone way that does not require
  a full enterprise configuration to demonstrate — freemium cannot
  carry products whose minimum viable unit is a paid contract.
- There is a credible differential value between free and paid that
  maps to a real customer growth axis (more seats, more volume, more
  advanced capability), not a synthetic limitation.
- The team can sustain the infrastructure and support cost of free
  users for long enough to observe conversion over multiple months.

## Execution Workflow

1. Start by naming the job the free tier does for the business. Common
   jobs: top-of-funnel acquisition, product-led distribution, network
   effect seeding, viral reach. If the team cannot pick one, freemium
   is premature and a trial is probably the better primitive.
2. Define the standalone value of free. A free tier that feels broken
   generates frustration, not affinity — the user must be able to use
   it for a real task and get real value, even if narrow.
3. Pick the upgrade boundary. The strongest boundary is one the user
   runs into because they are growing: more seats, more storage, more
   projects, more advanced features as the use case matures. Boundary
   choice determines whether upgrade feels natural or punitive.
4. Classify the structure. Feature-gated freemium holds advanced
   capability behind the paywall; volume-gated freemium caps a
   countable resource; user-gated freemium caps team size. Most
   freemium products blend two axes because a single axis leaks
   revenue or cuts off acquisition.
5. Calibrate the threshold. If the free tier is too generous, paid
   conversion stalls because users have no reason to upgrade. If it
   is too stingy, users churn before they experience enough value to
   want the paid tier. Early calibration is qualitative — interview
   users at the boundary and watch how they react.
6. Design the upgrade moment. The prompt to upgrade should appear at
   the exact instant the boundary matters — adding the fourth
   teammate, importing the fourth project, scheduling the second
   recurring export. The prompt language should acknowledge growth,
   not scold.
7. Use TodoWrite to log the free tier's job, the differential value
   list, the boundary axis, and the conversion target. Freemium
   without a target number drifts into "generous" and stays there.
8. Measure free-to-paid conversion over three, six, and twelve
   months. Healthy benchmarks for PLG SaaS are in the two to five
   percent range; higher suggests the free tier is too tight, lower
   suggests the paid tier isn't differentiated.

## Rules: Do

- Give the free tier a named job for the business; if there is none,
  use a trial instead.
- Make the free tier genuinely useful as a standalone product, not a
  feature-amputated sample.
- Place the paid boundary at a real growth axis — seats, volume,
  projects, advanced capability as sophistication grows.
- Show the upgrade prompt at the moment the user hits the boundary,
  not via nagging banners unrelated to their current task.
- Track conversion cohorts over time, not just the monthly aggregate;
  freemium converts on a long horizon.

## Rules: Don't

- Don't use dark patterns: hidden paid tiers, forced downgrades on
  trial expiry, punitive feature removal from previously-free users.
- Don't make the paid tier a minor polish pass over free; if the gap
  is not credible, nobody upgrades.
- Don't cap the free tier so tight that users never experience the
  product's core value; no aha moment means no upgrade path.
- Don't confuse freemium with trial. Trial has an expiry; freemium is
  indefinite. Mixing the two ("free forever, unless we change our
  minds") erodes trust faster than any feature removal.
- Don't ignore the support cost of free users. If support volume
  scales one-to-one with free users, freemium is a financial trap.

## Expected Behavior

After the skill, the team can answer three questions cleanly: what
does free do for the business, what is the upgrade boundary, and what
conversion rate signals health. The free tier stops being "the small
plan" and becomes a deliberate product with its own job. The paid
tier stops being "the tier with all the features" and becomes the
answer to a specific growth moment the customer has experienced.

Over a quarter, the distinction between freemium and trial becomes
operationally real — support triage, feature gating logic, and email
lifecycle all differentiate the two. Conversion rates are tracked as
cohort curves, not monthly averages, and the team is comfortable
saying "this cohort is underperforming, probably because we widened
the boundary in April."

## Quality Gates

- The free tier has a named business job (acquisition, distribution,
  network effect, virality) written in a sentence.
- Differential value between free and paid is spelled out feature by
  feature, not abstractly.
- The upgrade boundary aligns with a real customer growth axis.
- Free-to-paid cohort conversion is instrumented and tracked over at
  least three, six, and twelve month windows.
- The team has a documented stance on dark patterns — what they will
  never do — to prevent drift under revenue pressure.

## Companion Integration

Invoked by Matilha core skills when monetization is on the table.
Pairs tightly with `growth-pricing-psychology` (the tier above free
is designed via pricing psychology) and with `growth-value-metric`
(the upgrade boundary usually aligns with the chosen value metric).
Downstream of `growth-icp-definition` — the job of the free tier
depends on who the product is for.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: a named business job for the free tier, documented
  differential value, no dark patterns in the upgrade flow.
- Use "should" for: two to five percent free-to-paid cohort
  conversion as a healthy range for PLG SaaS, upgrade prompt tied to
  the boundary moment.
- Use "may" for: the specific structural mix (feature-gated,
  volume-gated, user-gated) and the absolute thresholds, which are
  product-specific.

## Troubleshooting

- **"Nobody upgrades from free"**: The paid tier is not
  differentiated enough or the boundary never gets hit. Interview
  power users on the free tier and ask what would make them upgrade;
  the honest answer is usually narrow and fixable.
- **"Free users are consuming huge infrastructure cost"**: The
  volume cap is misaligned. Revisit the boundary; freemium cannot
  subsidize heavy usage indefinitely.
- **"We added a free tier and paid revenue dropped"**: Cannibalization.
  The free tier probably overlaps too much with the paid tier. Trim
  the free tier's upper bound or move the boundary.
- **"Support volume exploded after launching free"**: Free users
  consume support at a similar rate to paid users. Either gate support
  by tier (email-only for free, chat for paid) or tighten the
  qualifying criteria for free accounts.

## Concrete Example

A design tool offers a free tier: unlimited personal files, three
editors per team, and two team files. The free tier is generous
enough to be useful for a freelancer and compelling enough to get
teams experimenting. The paid tier — Professional at fifteen per seat
per month — unlocks unlimited team files, shared component libraries,
and version history. The upgrade trigger is natural: the team adds a
fourth editor, spins up a fourth project, or wants a shared component
library. No dark pattern, no surprise paywall — the boundary aligns
with a real moment of growth, and the customer upgrades because the
product has become central to how they work, not because an email
nagged them.

## Sources

- `[[concepts/plg-estrategias-growth]]`
- `[[sources/product-growth-hacking]]`
- `[[concepts/jtbd-positioning]]`
- Inspired by the product-led growth literature (Kyle Poyar, Wes Bush)
  and the freemium chapters of the Product Growth Hacking source,
  paraphrased through Danilo's wiki synthesis of ethical-friction
  design and cohort conversion.
