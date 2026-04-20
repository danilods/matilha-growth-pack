---
name: growth-viral-loops
description: Use when designing referral or invite features — apply viral coefficient analysis and k-factor targets to evaluate loop viability.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a product team is considering a referral program, redesigning
invites, or debating whether "virality" is a realistic growth channel.
Fires when leadership says "let's build a refer-a-friend" without
understanding what a k-factor is or why most referral programs quietly
fail. The skill measures loop viability in quantitative terms, names the
cycle-time trade-off, and separates genuinely viral mechanisms from
incidental sharing.

## Preconditions

- The product has enough users to measure an invite flow — a loop cannot
  be validated on ten seed users.
- Instrumentation distinguishes invites-sent from invites-accepted, or
  can be extended to.
- The team accepts that k < 1 is normal and can be useful as an
  amplifier, even though only k > 1 is self-sustaining growth.

## Execution Workflow

1. Use Read on existing invite flows or sharing features. Note whether
   they are built as core product utility (a teammate collaborates), as
   incentivized referral (both sides get something), or as passive
   branding (a watermark, a "sent from" footer).
2. Compute the current k-factor. Take a recent cohort and measure two
   numbers: average invites-sent per user within a fixed window, and
   invite-to-signup conversion on the receiving end. Multiply. A k of
   0.2 means each user brings 0.2 new users through the loop; a k over
   1 means the loop sustains itself.
3. Measure cycle time alongside k. Cycle time is the average time from
   a user joining to the user sending their first invite. A k of 0.3
   with a one-week cycle beats a k of 0.7 with a three-month cycle
   over any realistic horizon, because compounding happens on the
   cycle, not on the raw coefficient.
4. Classify the loop type. Content loops ride on user-created artifacts
   that attract others (a share-able design). Collaborative loops ride
   on the product requiring teammates to deliver value (a shared
   document). Incentivized loops ride on two-sided reward. Network-
   effect loops ride on the product getting better with scale. Each
   type has different levers.
5. Pick the levers that match the loop type. Collaborative loops
   accelerate by making solo use feel incomplete until a teammate is
   added. Incentivized loops accelerate by making the reward matter to
   both sides. Content loops accelerate by removing friction from
   sharing and increasing artifact reach. Do not mix levers across loop
   types; each has its own failure mode.
6. Set ethical boundaries up front. The goal is genuine utility, not
   manufactured invitations. Auto-importing contacts and sending
   surprise emails in the user's name tanks the goodwill reservoir and
   often creates a larger long-term problem than the short-term lift.
7. Use Edit to implement the invite mechanism at a natural moment in
   the product — post-aha, post-delight, post-need-a-teammate — rather
   than as a generic banner. Timing is most of the k-factor.
8. Re-measure at the next cohort. Track k and cycle time together;
   either alone is misleading.

## Rules: Do

- Measure k and cycle time as a pair; optimize whichever is the current
  bottleneck.
- Pick one loop type and build for it; mixed-type loops dilute levers
  and confuse measurement.
- Trigger invites at moments of genuine utility or delight, not at
  arbitrary sign-up-day-one prompts.
- Make the invite itself useful to the recipient — a shared artifact,
  a teammate onboarding, a working link — not a bare "come try this."
- Treat sub-unity k as an amplifier: a k of 0.4 on paid or organic
  acquisition effectively adds forty percent to every acquired user
  over the cycle.

## Rules: Don't

- Don't confuse sharing with virality. A share button without a
  sign-up hook is a branding moment, not a loop.
- Don't spam contact imports or send invites in the user's name without
  clear consent — the short-term lift is real and the long-term cost
  is larger.
- Don't target k > 1 as a hard requirement; most successful loops sit
  below that and amplify other channels rather than replacing them.
- Don't build incentivized referral without two-sided reward;
  single-sided bribes convert the sender and disappoint the receiver.
- Don't measure a loop for a week and call it; loops need at least a
  full cycle-time window plus a cohort to stabilize.

## Expected Behavior

After applying the skill, the team speaks about virality in numbers
rather than vibes. The invite flow has a named loop type and a target
k-cycle pair. Decisions get sharper: a proposed "refer-a-friend" that
would take three months of engineering to raise k from 0.2 to 0.25 gets
compared against shortening cycle time, which is often a smaller change
with a larger effect.

Referral stops being a checkbox and becomes a design surface. Product
and growth think together about where the invite should trigger, what
the invite should do for the recipient, and whether the loop type
matches the product's natural grain. Most of the ethical pitfalls never
get built because the framework surfaces them before implementation.

## Quality Gates

- The current k-factor and cycle time are both measured and reported,
  not just one.
- The loop type is named (content, collaborative, incentivized, or
  network-effect) and the levers match that type.
- The invite is triggered at a utility or delight moment, not on a
  generic banner.
- Two-sided reward is in place whenever the loop uses incentives.
- Invitee consent is explicit; no dark-pattern contact import.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
referral or sharing features are in scope. Pairs with
`growth-plg-strategy` (collaborative products pass the viral-surface
test and unlock loop types sales-led products cannot use) and
`growth-activation-aha-moment` (invites triggered post-aha convert
better than invites triggered pre-aha). Does not delegate to other
packs in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: measuring k-factor and cycle time together, explicit
  invitee consent.
- Use "should" for: triggering invites at utility or delight moments,
  two-sided reward on incentivized loops.
- Use "may" for: the specific reward magnitude or the choice between
  competing loop types when the product supports more than one.

## Troubleshooting

- **"The k-factor looks low but growth is strong"**: Growth may be
  coming from channels other than the loop. Separate loop-attributable
  growth from paid and organic before blaming or crediting the loop.
- **"We ran an incentive and k moved, then moved back"**: Incentive
  pulls forward invites that would have happened anyway; confirm the
  lift persists past the incentive window before declaring success.
- **"Invitees sign up but don't stick"**: The loop is measuring
  sign-ups, but your retention analysis should be counting invitee
  activation. Invitees often have lower intent than organic users;
  adjust the conversion target accordingly.
- **"Sales says viral is embarrassing for enterprise buyers"**: That
  is a valid signal that the loop type is wrong for the buyer. A
  collaborative loop is often acceptable where an incentivized one is
  not.

## Concrete Example

A cloud-storage product runs a two-sided loop — inviter and invitee
each receive a bonus on successful sign-up. The loop is collaborative
and incentivized at the same time, triggered immediately after a user
saves their first file to a shared folder (a utility moment). Invite
mechanics are simple: a share link with a human-readable preview, no
forced contact import, explicit copy that tells the inviter what the
invitee will see. The measured k-factor sits around 0.6 with a
two-day cycle time — below self-sustaining but a powerful amplifier
on every other channel. By contrast, an earlier version that
auto-imported contacts and sent invitation emails in the user's name
produced a short-term k spike followed by a trust crash and a sustained
decline in organic sign-ups; the current design is smaller on paper
and larger on the compounded result.

## Sources

- `[[sources/product-growth-hacking]]`
- `[[concepts/plg-estrategias-growth]]`
- `[[concepts/aarrr-growth-metrics]]`
- Inspired by the viral-loop and k-factor literature from Dropbox,
  PayPal, and LinkedIn growth histories, paraphrased further through
  Danilo's wiki synthesis of loop-type taxonomy and cycle-time
  trade-offs.
