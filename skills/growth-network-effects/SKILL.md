---
name: growth-network-effects
description: Use when evaluating competitive moat — identify direct vs indirect network effects and design product for compounding defensibility.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when the team is reasoning about competitive defensibility and
someone claims the product has "network effects" without being
precise about the mechanism. Fires when investor decks or strategy
memos invoke the phrase as a talisman — shorthand for "we will win"
— without naming which users value which other users' presence, or
which complement gets more valuable as the network grows. The skill
tests the claim, distinguishes real network effects from scale
economies or brand advantages, and turns the test into product
decisions that either strengthen the mechanism or stop pretending it
exists.

## Preconditions

- A candidate network-effect claim is on the table; otherwise the
  skill has nothing to evaluate.
- The team can describe concretely how one user's presence changes
  another user's experience — if nobody can finish that sentence,
  the claim fails the first gate.
- There is data or a credible proxy for the marginal value each new
  user brings to the existing base; qualitative reasoning alone is
  not enough for a strategic decision.

## Execution Workflow

1. Name the mechanism precisely. For each candidate network-effect
   claim, finish the sentence "user A gets more value because user B
   is also on the product, specifically because __." If the blank
   cannot be filled, there is no network effect — there may be a
   scale economy, a brand effect, or a data advantage, but not a
   network effect.
2. Classify as direct or indirect. Direct network effects: users
   value each other's presence directly — communication tools,
   social networks, collaboration platforms. Indirect (two-sided)
   network effects: users value a complement that grows with the
   network — marketplaces, where more sellers attract more buyers,
   which in turn attract more sellers.
3. Check for confusion with scale. Scale economies (cheaper per unit
   at volume), data advantages (more data means better model), and
   brand advantages (more awareness means cheaper acquisition) are
   all moats, but they are not network effects. Mislabeling them
   inflates the strategic narrative and leads to bad product
   decisions downstream.
4. Stress-test the cold-start. Network effects are worth little
   before critical mass. The product must have standalone value or
   a seeding strategy that survives the period when the network is
   thin. Two-sided markets have especially hard cold-starts and
   often need a pre-seeded side.
5. Design for compounding. If the network effect is real, the product
   should make adding to the network a natural byproduct of using it
   — collaboration invites, shared artifacts, public content that
   seeds discovery. Growth loops that use network effects as the
   substrate are the compounding form of this mechanism.
6. Audit for asymmetry. Some users in a network are worth far more
   than others — creators in a content network, sellers in a
   marketplace, power users in a collaboration tool. The product
   should protect and reward the asymmetric side, because losing
   them collapses the other side fast.
7. Use TodoWrite to document the mechanism, the classification, the
   cold-start status, and the compounding design choices. Without
   this, the team's network-effect story drifts with each new
   audience.
8. Revisit quarterly. Competitive pressure can erode network effects
   that were real a year ago — users can belong to multiple
   networks, and network-effect moats are strongest when
   multi-homing is costly.

## Rules: Do

- Name the network-effect mechanism in a precise sentence before
  making any strategic claim on it.
- Separate network effects from scale, data, and brand advantages;
  each is a distinct moat with distinct implications.
- Plan for cold-start. Standalone utility or pre-seeded network are
  the usual solutions.
- Design product features that make inviting or contributing a
  natural byproduct of use, not a separate action.
- Protect the asymmetric side when one exists — creators, sellers,
  power users carry the network.

## Rules: Don't

- Don't claim network effects where users do not value each other's
  presence. Storage, productivity utilities, and many SaaS tools
  have scale economies but no network effect.
- Don't assume direct and indirect network effects behave the same.
  Two-sided markets have harder cold-starts and require different
  seeding strategies than one-sided direct networks.
- Don't confuse viral growth (high k-factor) with network effects.
  A viral loop grows the user base; a network effect makes the
  product more valuable as the base grows. They often coexist, but
  they are not the same.
- Don't ignore multi-homing risk. If users can be on the product
  and on a competitor at zero marginal cost, the network effect is
  weaker than it looks.
- Don't lean on "network effects" in a pitch without being able to
  show the mechanism. Sophisticated audiences see through the
  claim.

## Expected Behavior

After the skill, the team talks about defensibility with precision.
Every claim of a network effect comes paired with a sentence about
the mechanism. Product decisions route toward features that
strengthen the mechanism — collaboration-native data models, shared
artifacts, public content — and away from features that would be
nice but don't compound. Investors and partners get a story that
survives the first skeptical question.

Over time, the team separates defensibility into its component
moats: network effects here, scale economies there, data advantages
in a third place, brand in a fourth. Each moat is worked on
deliberately, and the product strategy stops relying on a single
mystical phrase.

## Quality Gates

- The network-effect mechanism is stated in a concrete sentence
  with user roles named.
- The claim is classified as direct or indirect, and the
  implications for cold-start are acknowledged.
- Other moats (scale, data, brand) are separated out and labeled
  correctly.
- Product features that strengthen the mechanism are named; if
  there are none, the claim is likely weaker than the team thinks.
- Multi-homing risk is considered, and the team can say whether the
  network effect is strong enough to prevent it.

## Companion Integration

Invoked by Matilha core skills (`matilha-plan`, `matilha-scout`)
when defensibility discussions enter scope. Pairs with
`growth-viral-loops` (viral loops amplify but do not constitute
network effects) and with `growth-category-creation` (category
dominance often relies on network-effect claims that must be
honest). Downstream of `growth-positioning-strategy` — the
positioning story can or cannot honestly invoke network effects.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: explicit mechanism statement, classification as
  direct or indirect, separation from scale and brand advantages.
- Use "should" for: quarterly re-audit of network-effect strength,
  protection of the asymmetric side, standalone utility before
  critical mass.
- Use "may" for: the specific seeding strategy, the specific
  collaboration features, the specific content formats — these are
  product-specific.

## Troubleshooting

- **"We claim network effects but cannot describe the mechanism"**:
  Either it is a scale economy in disguise or the product
  genuinely has no network effect. Be honest internally before the
  next investor conversation.
- **"We have network effects but growth is stalling"**: The cold
  start was survived but the product may have hit a multi-homing
  ceiling. Check whether users are also on a competitor; network
  effects weaken fast when multi-homing is free.
- **"The asymmetric side is leaving"**: The side that carries the
  network (creators, sellers, power users) feels under-rewarded.
  Their churn will collapse the other side on a lag; prioritize
  before the visible number moves.
- **"A new competitor with a different mechanism is gaining
  ground"**: Network effects from one mechanism do not defend
  against a fundamentally new one. Assess whether the competitor's
  mechanism is stronger rather than assuming the existing moat
  holds.

## Concrete Example

Two design tools compete. The predecessor ships single-user files,
polished and technically excellent, and grows on craft and brand.
The successor ships a browser-native collaborative canvas where
every design is a live multi-user document. The mechanism is
direct: every new user becomes a potential collaborator for the
existing base, and every shared file is a viral seed into new
teams. Even with a less polished initial feature set, the successor
compounds in a way the predecessor cannot — technical excellence
does not offset a network-effect gap. Over a few years the market
tips. The lesson is not that craft is unimportant; it is that a
network effect, once it starts compounding, becomes a form of
defensibility that product quality alone cannot match.

## Sources

- `[[sources/product-htrategy]]`
- `[[concepts/plg-estrategias-growth]]`
- `[[concepts/jtbd-positioning]]`
- Inspired by the network-effects literature (NfX, Hamilton
  Helmer's 7 Powers) and the defensibility chapters of the Product
  Strategy source, paraphrased through Danilo's wiki synthesis of
  mechanism-first classification and asymmetric-side protection.
