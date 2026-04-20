---
name: growth-pricing-psychology
description: Use when designing pricing tiers — apply anchoring, decoy effect, price-quality signals, and round-number bias to structure optimal tier architecture.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team is about to publish a pricing page, restructure
existing tiers, or argue about whether to add a third option. Fires
when the conversation is dominated by gut feel ("this price feels
right") or by pure cost-plus math that ignores how buyers actually
perceive the ladder of options. The skill reframes pricing design as a
perception problem — what the page communicates before the customer
reads a single feature bullet — and turns that into a concrete tier
layout, price-ending policy, and anchoring sequence.

## Preconditions

- Some willingness-to-pay signal exists, even if rough: past quotes,
  competitor pricing, early-customer conversations, or a planned van
  Westendorp survey.
- There is a real product with at least two meaningful units of value
  that can be packaged differently (features, seats, volume).
- The team can run a tier change for at least a full sales cycle to
  read the conversion delta cleanly.

## Execution Workflow

1. Start by listing the actual differential value between tiers. A
   tier that costs more must unlock something the buyer can point to;
   if the list is weak, the tier needs redesign before any psychology
   is layered on top.
2. Decide the tier count. Two tiers rarely create enough structure for
   anchoring; four or more invite paradox-of-choice paralysis. Three
   is the default, with a deliberate role for each: entry, target,
   anchor.
3. Design the anchor tier. This is the top option, typically the one
   most visible on the page. Its job is to set the upper bound of the
   product's perceived value so the middle tier reads as reasonable.
   The anchor does not need to sell in volume; it needs to be visible.
4. Design the target tier. This is the one most customers should buy.
   Give it the best value-per-dollar on the page, the "Most Popular"
   badge if the brand permits, and the feature set that matches the
   modal customer's job to be done.
5. Design the entry tier. It should deliver real value on its own, not
   feel crippled — the job is to get the customer into the product,
   not to trap them. If the entry tier feels punitive, customers route
   around it to a competitor instead of upgrading.
6. Consider a decoy. Ariely's classic case — a third option that is
   strictly dominated by the target tier — can shift preference
   toward the target without any change to the target itself. Use
   sparingly and only where the decoy is honest; a decoy should look
   like a real option, not a trick.
7. Set price endings deliberately. Endings in .99 or .95 signal
   discount and volume; round endings signal premium and consideration.
   The ending is a tiny signal but the whole page must agree with
   itself — mixing $99 with $1,000 without a reason confuses the
   brand story.
8. Use TodoWrite to capture the tier table, the anchor rationale, the
   target tier's differentiating value, and the measurement plan.
   Pricing without a measurement plan is a guess.
9. Ship and observe for at least one full sales cycle. Conversion rate
   per tier, average revenue per account, and downgrade rate are the
   core reads.

## Rules: Do

- Build the tier ladder with a named role for each rung: entry,
  target, anchor.
- Make the anchor tier visible even if it does not sell; its job is
  perceptual, not volumetric.
- Keep the entry tier genuinely useful — a gateway, not a trap.
- Align price endings with brand story; premium products use round
  numbers, volume products use .99 tails.
- Test pricing with willingness-to-pay research (van Westendorp or
  similar) before launch when the stakes are high.

## Rules: Don't

- Don't copy the competitor's pricing structure without mapping it to
  your own differential value; same structure with different value is
  worse than a bespoke structure.
- Don't rely on fake strikethroughs or phantom discounts to anchor;
  the short-term conversion bump is paid back in trust erosion and,
  increasingly, regulatory risk.
- Don't confuse a decoy with a third real product. A decoy the team
  secretly hopes no one buys is a warning sign the middle tier is
  under-built.
- Don't ship more than three to four tiers without a segmentation
  reason; the paradox of choice shows up fast on pricing pages.
- Don't treat the price as a feature; customers read the whole page
  holistically, and a cheap price on a weak page reads as cheap, not
  as a deal.

## Expected Behavior

After the skill, the pricing page communicates a clear value ladder
rather than a menu of options. The anchor tier elevates perceived
product quality; the target tier reads as the obvious choice for the
modal customer; the entry tier invites without trapping. Sales and
product stop arguing about "the right price" and start arguing about
which tier carries which job, which is a much more productive
conversation.

Over a quarter, average revenue per new account typically moves in
response to tier redesign even when total conversion is flat — the
mix shifts toward the target tier. Teams that measure per-tier
conversion and not just aggregate signups can attribute the change
cleanly.

## Quality Gates

- Each tier has a named role (entry, target, anchor) and a one-line
  rationale.
- The target tier has demonstrably better value-per-dollar than entry
  and anchor, and the page makes that visible.
- Price endings are consistent with the brand story across the whole
  page.
- A measurement plan exists: per-tier conversion, ARPA, and downgrade
  rate tracked for at least one sales cycle.
- Willingness-to-pay research or a credible proxy (competitor data,
  quote history) grounds the absolute price points.

## Companion Integration

Invoked by Matilha core skills (`matilha-plan`, `matilha-scout`) when
monetization decisions enter scope. Pairs closely with
`growth-value-metric` (value metric choice precedes tier pricing) and
with `growth-freemium-strategy` (freemium is a specific case of entry
tier design). Downstream of `growth-icp-definition` — the modal
customer determines which tier is the target.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: named role per tier, measurement plan before
  launch, honest anchor (no fake discounts).
- Use "should" for: three-tier default, willingness-to-pay research
  before large pricing changes, round-number endings for premium
  positioning.
- Use "may" for: decoy tier inclusion, "Most Popular" badging,
  annual-versus-monthly split.

## Troubleshooting

- **"Our middle tier doesn't convert better after adding the
  anchor"**: The anchor may not be credible — if it looks like a
  placeholder, it does not shift perception. Strengthen the anchor's
  feature set or re-price it to a defensible number.
- **"Customers keep asking for a tier between entry and target"**:
  The gap is too wide. Either the entry is too weak or the target is
  too ambitious. Re-examine differential value before adding a
  fourth tier.
- **"The decoy is actually selling"**: It is not a decoy; it is a
  product. Rename it, reposition it, and treat it as a real tier,
  because your customers do.
- **"Downgrade rate spiked after repricing"**: The target tier's
  differential value did not keep pace with the price change.
  Customers downgrade when they feel they are paying for air.

## Concrete Example

A B2B SaaS ships two tiers — Free and Pro at $20 per month. Free-to-
Pro conversion sits at around two percent for months. The team adds a
third tier — Business at $99 per month — with audit logs, SSO, and
role-based access that enterprise buyers actually want. Pro now reads
as mid-range rather than expensive. Most signups do not buy Business,
but its mere presence changes how the page reads. Free-to-Pro
conversion climbs to roughly five percent over the next two months
without any change to the Pro tier's features or price. The lift is
pure anchoring plus a light decoy effect — Business makes Pro feel
like the obvious choice.

## Sources

- `[[sources/product-growth-hacking]]`
- `[[concepts/frameworks-comportamentais]]`
- `[[concepts/tomada-decisao]]`
- Inspired by Dan Ariely's decoy-effect work (the classic Economist
  magazine case), Robert Cialdini's anchoring literature, and the
  pricing chapters of the Product Growth Hacking source, paraphrased
  through Danilo's wiki synthesis of tier-role design and
  measurement cadence.
