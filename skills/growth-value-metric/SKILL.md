---
name: growth-value-metric
description: Use when picking pricing dimension — identify the metric that scales with customer value (seats, usage, volume) so revenue grows as customer succeeds.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when the team needs to pick, change, or justify the unit the
product is priced by — per seat, per contact, per transaction, per
gigabyte, per API call. Fires when pricing conversations bog down in
absolute numbers without resolving the deeper question of what axis
the price scales along. The skill moves the conversation upstream: the
axis must track the customer's own definition of success, so that when
they grow, the account grows, and when they struggle, the bill
shrinks automatically instead of feeling like extortion.

## Preconditions

- The team can describe what a successful customer looks like one year
  in — what they have more of, what they do more often, what they
  stopped doing manually.
- Usage telemetry exists or can be built to confirm which candidate
  metric actually correlates with retention and expansion.
- Leadership is willing to consider changing the pricing axis, not
  just the absolute dollar amount; the two decisions are often
  entangled.

## Execution Workflow

1. List the candidate axes. For most SaaS products, candidates are
   per seat, per contact, per transaction, per volume (GB, rows,
   tokens), per integration, or some fixed platform fee plus a
   variable rider.
2. For each candidate, ask three questions. First: is it
   understandable to the buyer — can they estimate their bill without
   a spreadsheet? Second: does it grow with the customer's own
   success — when they win, does it scale up? Third: is it hard to
   game down — if the customer wants to lower their bill, can they
   do so only by using the product less, or by creative re-labeling?
3. Cross-reference with usage data. Plot candidate metrics against
   retention, expansion, and churn. The metric that correlates most
   strongly with long-term retention is the closest proxy for
   customer value — pricing on it aligns revenue with that value.
4. Check for anti-patterns. Pricing per "active user" incentivizes
   hiding accounts; pricing per "feature used" incentivizes not
   using the product; pricing per "connected integration" works only
   if integrations are genuine value drivers, not check-the-box
   features.
5. Consider graduated pricing. A lower per-unit rate at higher
   volumes signals partnership — the customer's scale is a shared
   win. Flat per-unit pricing at scale is rarely competitive and
   reads as "we want you to stop growing here."
6. Consider mixed metrics. A fixed platform fee plus a variable rider
   lets the business capture baseline value and upside together.
   Payment processors, cloud infrastructure, and some analytics
   products are natural mixed-metric cases.
7. Use TodoWrite to document the chosen metric, the alternatives
   considered, the anti-patterns avoided, and the expected impact on
   customer segments — some customers win, some lose, and the team
   should know which.
8. Pilot the new pricing with a small cohort before full rollout.
   Value metric changes ripple through contract renewals for years;
   a short pilot catches structural mistakes early.

## Rules: Do

- Pick a metric that the buyer can estimate without a spreadsheet and
  that grows when they succeed.
- Test candidate metrics against retention and expansion data before
  choosing; the best metric is rarely obvious without that lens.
- Use graduated pricing at higher volumes to signal partnership
  instead of punishment.
- Consider mixed metrics (platform fee plus variable) when no single
  axis captures the product's full value arc.
- Document the metric's semantics precisely — "contact" means what,
  exactly — to prevent renewal-time arguments.

## Rules: Don't

- Don't price on a metric the customer has to distort the product to
  reduce. Any metric that rewards hiding users, avoiding features,
  or gaming logs will be gamed.
- Don't price per seat on a product where the unit of success is per
  project; the metric is mis-aligned and customers will feel it.
- Don't change the value metric silently at renewal; if the axis is
  changing, the conversation is a pricing change, not an adjustment.
- Don't pick a metric nobody on the team can explain in a sentence; if
  the team struggles, the buyer will struggle more.
- Don't assume the metric that worked at the first hundred customers
  will work at the ten thousandth; value metrics age.

## Expected Behavior

After the skill, the team can name the single axis the product prices
along and defend it from three angles: understandability, alignment
with customer success, and resistance to gaming. Renewal conversations
stop being about price and become about growth ("your contact list
grew, here's your new bill"), which is a much easier conversation to
have. Expansion revenue becomes a natural byproduct of customer
success rather than a separate sales motion.

Over quarters, the team develops a cohort view of value-metric fit.
Customers whose value-metric bills scale smoothly with their own
success metrics are the healthiest accounts; misalignment shows up
as either surprise bills (customer angry) or capped bills at low
utilization (business underpaid).

## Quality Gates

- Three candidate metrics were evaluated, not one.
- The chosen metric has been correlated with retention and expansion
  in the available data.
- Anti-patterns (incentive misalignment, gamability) have been
  explicitly checked and ruled out.
- The metric's semantics are documented in contract-ready language,
  not marketing language.
- A pilot cohort has been defined, or rollout is staged by segment.

## Companion Integration

Invoked by Matilha core skills when pricing is in scope. Pairs with
`growth-pricing-psychology` (tier architecture layers on top of the
value-metric choice) and with `growth-freemium-strategy` (the free-
to-paid boundary typically sits on the value metric axis). Downstream
of `growth-icp-definition` — the value metric must match how the ICP
measures their own success.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: three candidate metrics evaluated, correlation
  with retention checked, anti-patterns ruled out.
- Use "should" for: graduated pricing at higher volumes, mixed
  metrics when no single axis captures the value arc.
- Use "may" for: the specific metric chosen and the absolute rate,
  which are product-specific.

## Troubleshooting

- **"Customers complain the bill is unpredictable"**: The value
  metric may be technically correct but cognitively too abstract for
  the buyer. Consider a floor plus a variable rider, or add a usage
  estimator to the pricing page.
- **"Big customers are capping usage to avoid overages"**: The
  per-unit rate at high volumes is not competitive. Graduated
  pricing can convert a cap into expansion.
- **"Expansion revenue is flat even as customers grow"**: The value
  metric is not tracking the growth axis. Usage grew on a dimension
  the product does not bill on; re-examine the axis.
- **"The metric incentivizes weird behavior"**: Either the metric
  is mis-chosen (hidden users, unused features) or the definition
  is too loose (customers re-labeling records to avoid counts).
  Tighten semantics or change the axis.

## Concrete Example

A marketing automation tool prices per seat — fifty per user per
month. A customer scales a marketing team from five to fifty users,
watches the bill climb from two-fifty to twenty-five-hundred a month,
and notices the marginal utility of the fiftieth user is nearly zero.
The value metric is mis-aligned: the unit of value is the contact
database, not the marketer operating it. The team shifts to per-
contact pricing — a fixed rate per ten thousand contacts with
graduated discounts at higher volumes. The customer now pays more
only when their addressable audience grows, which is a direct signal
of business success. The bill becomes predictable, the relationship
reads as partnership, and expansion revenue grows naturally as
customers build larger lists.

## Sources

- `[[sources/product-growth-hacking]]`
- `[[concepts/plg-estrategias-growth]]`
- `[[concepts/aarrr-growth-metrics]]`
- Inspired by Patrick Campbell's value-metric work at ProfitWell and
  the pricing-axis chapters of the Product Growth Hacking source,
  paraphrased through Danilo's wiki synthesis of graduated pricing
  and gamability analysis.
