---
name: growth-plg-strategy
description: Use when choosing growth model for SaaS or B2B — evaluate product-led vs sales-led vs hybrid positioning based on product complexity and buyer psychology.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a SaaS or B2B team is debating whether to self-serve, hire
account executives, or run a hybrid motion. Fires when leadership says
"we should be more like Figma" without asking whether the product
supports the same motion, or when a sales-led team is losing mid-market
deals that a PLG competitor is closing asynchronously. The skill
evaluates the product honestly against the prerequisites for each motion
and recommends the fit, which is often hybrid.

## Preconditions

- The product exists in rough form; PLG viability cannot be assessed from
  a deck.
- The buyer persona and typical decision process are at least roughly
  known — who signs, who approves, who pays.
- The team is willing to hear "PLG is the wrong fit" or "sales-led is the
  wrong fit" as an answer, not just a preferred answer.

## Execution Workflow

1. Use Read on onboarding docs, trial flows, and sales playbooks to
   understand how users currently reach value. Note how long it takes a
   new user, alone, to get to a moment where the product works for them.
2. Run the time-to-value test. Can a typical user reach a first-value
   moment in under fifteen minutes, without a human on the call? If yes,
   PLG is plausible. If it takes a data engineer, a security review, and
   an implementation partner, PLG is unlikely for that segment.
3. Run the self-serve test. Can a user sign up, configure, and use the
   product without contacting anyone? Look specifically for hidden
   blockers: SSO that requires a sales handshake, pricing that forces a
   quote, data imports that need a human.
4. Run the buyer-psychology test. Is purchase a single-user decision, a
   team-level decision, or a procurement-committee decision? Each moves
   the motion: individual buyers favor PLG, teams favor hybrid,
   procurement-heavy buyers favor sales-led by necessity.
5. Run the viral-surface test. Does the product get better or more useful
   as more teammates use it? Collaboration products (Figma, Notion)
   compound; single-seat tools do not. Compounding products are better
   PLG candidates because invitation is a feature, not an ask.
6. Synthesize a motion recommendation. Pure PLG fits when all four tests
   come back green. Sales-led fits when complexity, procurement, or
   implementation dominate. Hybrid fits when PLG can capture the individual
   and small-team layer but sales is needed to close mid-market and up.
7. If the recommendation is hybrid, define the PLG-to-sales handoff.
   What plan size or usage threshold triggers a human? What data does
   sales need? A handoff that is undefined produces both a leaky PLG
   funnel and a confused sales motion.
8. Use TodoWrite to draft the motion transition plan. PLG requires
   investment in onboarding, pricing page, and in-product conversion.
   Sales-led requires investment in lead qualification, SDR tooling, and
   enterprise features. The fit determines where the next dollar goes.

## Rules: Do

- Evaluate the product as it is, not as the roadmap hopes it will be —
  PLG demands the current version pass the tests.
- Pick hybrid deliberately, not by default. A vague hybrid is worse than
  either pure motion.
- Define the handoff threshold explicitly when going hybrid (seat count,
  revenue band, plan tier, or usage indicator).
- Match pricing structure to motion. PLG needs transparent, public
  pricing. Sales-led can use quote-based pricing. Hybrid needs both: a
  self-serve tier and a sales-contact tier.
- Revisit the choice when the ICP shifts — motion fit is a function of
  who the buyer is, not just what the product does.

## Rules: Don't

- Don't copy the motion of a successful competitor without running the
  four tests on your own product; many PLG attempts fail because the
  product is not actually PLG-ready.
- Don't call a product PLG while hiding pricing behind "contact sales" —
  that is sales-led with extra steps.
- Don't force a PLG motion on a product whose value requires a
  six-month integration; users will not survive the gap.
- Don't let PLG and sales-led teams compete for the same account
  silently; the handoff must be mechanical, not political.
- Don't treat PLG as a cost-saving play — it shifts investment from sales
  headcount to onboarding, pricing, and product work. It is cheaper per
  deal, not cheaper overall.

## Expected Behavior

After applying the skill, the team stops arguing about headcount and
starts arguing about product readiness, which is the useful conversation.
A green-across-the-board PLG product gets investment in onboarding,
empty states, and self-serve upgrade paths. A red-across-the-board
product gets investment in outbound, enterprise features, and a proper
sales-engineering function. A mixed result gets a defined hybrid motion
with a named handoff.

Sales and product stop fighting over who owns the user. In a well-run
hybrid, the product owns the first-value experience, and sales owns the
moment the account exceeds the self-serve envelope. Funnel numbers become
legible because each stage knows what motion it is optimizing.

## Quality Gates

- The recommendation is stated as one of pure PLG, pure sales-led, or
  defined hybrid — never "we should do both."
- The time-to-value, self-serve, buyer-psychology, and viral-surface
  tests each have a documented answer.
- If hybrid, the handoff threshold is named in concrete units (seats,
  dollars, usage).
- Pricing structure matches the motion: public transparent pricing for
  PLG, quote-based for sales-led, both-with-a-line for hybrid.
- The next quarter's investment is allocated to the work the chosen
  motion actually needs.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
product and business motion decisions surface. Pairs with
`growth-activation-aha-moment` (PLG only works when activation is fast)
and with `growth-viral-loops` (collaborative products pass the
viral-surface test more readily). Does not delegate to other packs in
v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: running all four tests before recommending a motion,
  naming a handoff threshold when going hybrid.
- Use "should" for: transparent pricing for PLG tiers, explicit
  investment reallocation to match the motion.
- Use "may" for: the specific segmentation inside hybrid (per-seat
  upsell, enterprise SKU, services) depending on the buyer profile.

## Troubleshooting

- **"We are PLG but conversion is terrible"**: Check the tests again.
  Often one is red — usually self-serve is blocked by a quote-based
  upgrade flow — and the motion is hybrid in disguise.
- **"Enterprise deals are stuck at procurement"**: PLG did its job (got
  the user in); what is missing is the sales motion for the larger
  commit. Define the handoff and hire accordingly.
- **"The product is too complex for PLG"**: Sometimes the honest answer
  is "today yes, but an onboarding overhaul would change that." The
  skill asks for current reality, not eternal verdict.
- **"Different segments want different motions"**: That is a classic
  hybrid case. Segment the funnel, not just the sales team; the product
  itself should know whether a given user is self-serve-eligible.

## Concrete Example

A B2B data-pipeline tool debates whether to go PLG. Time-to-value test:
average new user takes two days to run a first pipeline, mostly because
source connection requires an OAuth scope that IT must approve.
Self-serve test: onboarding demands a data engineer and someone with
backend access. Buyer psychology: purchase is approved by a platform lead
and procurement. Viral surface: the tool is single-team and does not get
more useful with more teammates. Three reds, one mixed — pure PLG is off
the table. The team lands on hybrid: a scoped-down "sandbox" plan that a
single engineer can run in under fifteen minutes for evaluation (PLG
funnel), with a defined handoff to sales when the sandbox is promoted
to a production workload. The product investment focuses on the
sandbox onboarding; the sales investment focuses on the promotion
handshake.

## Sources

- `[[concepts/plg-estrategias-growth]]`
- `[[sources/product-growth-hacking]]`
- Inspired by Wes Bush's PLG framework and the bottom-up adoption
  literature, paraphrased further through Danilo's wiki synthesis of
  time-to-value, self-serve, and buyer-psychology tests.
