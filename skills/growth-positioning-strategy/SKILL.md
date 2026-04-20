---
name: growth-positioning-strategy
description: Use when defining competitive positioning — combine Ries' category positioning with Christensen's JTBD lens for sharp market differentiation.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team needs to sharpen how the product is described to the
market — whether writing the homepage hero, briefing sales, or
deciding which features to foreground. Fires when the team notices
that prospects leave calls unclear on what the product is "for," or
when sales close rate stays flat despite more leads. Positioning is
the layer above messaging: it sets the frame that every downstream
asset must reinforce. This skill produces a positioning statement
that the whole team can recite and defend.

## Preconditions

- The product has at least a small set of paying or successfully
  activated users whose "switch narrative" can be reconstructed — raw
  speculation about positioning with zero real customers tends to
  produce wishful statements that crumble on contact with the market.
- The team can name the real alternatives users would pick if the
  product did not exist, including non-obvious ones like spreadsheets,
  internal tools, and "do nothing."
- Leadership is willing to exclude segments. Positioning that tries to
  speak to everyone reaches no one.

## Execution Workflow

1. Use Read on recent win/loss interview notes and sales transcripts.
   Identify the 3 most common "job" statements users cite when they
   describe why they bought. Strip out feature language.
2. Build a candidate statement using the template: "For [ICP],
   [product] is a [category] that [value delivered] unlike
   [alternatives] because [differentiation]." Draft three variants,
   each foregrounding a different dimension.
3. Stress-test against Ries' Law of the Category. Is the category
   already owned by a dominant player? If yes, invent a subcategory
   where the product is first-to-mind, or pick a narrower ICP. Second
   place in an existing category rarely wins.
4. Apply the JTBD filter. Does the statement name the job the user is
   hiring the product to do, or does it list features? Rewrite feature
   language into outcome language — what the user gets done, not what
   the product does.
5. Check defensibility. The differentiation clause must be credibly
   defensible — a capability, data asset, community, or timing edge
   that a well-funded copycat cannot trivially replicate. If the only
   differentiator is "we're cheaper" or "we have feature X," the
   statement is weak.
6. Run it past 5 ICP-matching prospects in a low-stakes channel. Ask:
   "In your own words, what does this product do?" Compare their
   paraphrase to the intended statement. Drift signals ambiguity.
7. Lock the statement. Propagate it to homepage hero, sales deck cover
   slide, onboarding welcome copy, and investor deck one-liner. One
   statement, repeated coherently, beats five polished but divergent
   versions.
8. Review yearly. Markets shift, ICP matures, categories fragment. A
   positioning statement that was sharp two years ago may have drifted
   into generic territory as competitors copied the language.

## Rules: Do

- Position against the prospect's mind, not against the product's feature
  list — Ries' core insight is that positioning is a perception game.
- Name the job the product is hired for, in the user's language,
  before naming features or technology.
- Include credible, hard-to-copy differentiation; a statement that
  rivals could paste into their own homepage has no positioning value.
- Pick a narrower ICP than feels comfortable. Sharp beats broad every
  time for early and mid-stage products.
- Include non-obvious alternatives (spreadsheets, internal tools, "do
  nothing") — most real competition lives there, not in the named
  competitor set.

## Rules: Don't

- Don't try to occupy a category that is already firmly owned — invent a
  subcategory where the product can be first-to-mind, or reposition.
- Don't lead with features ("we have X, Y, Z"). Lead with the job being
  done better than alternatives.
- Don't write a statement you can't imagine a real customer repeating.
  If it sounds like marketing boilerplate, it is.
- Don't reposition every quarter. Positioning compounds over years;
  repositioning is painful and erases accumulated mindshare.
- Don't skip the differentiation clause. "What we do" without "why we
  do it better than alternatives" is description, not positioning.

## Expected Behavior

After applying the skill, the team stops having circular debates about
"what we are." Homepage, sales deck, pricing page, and onboarding
welcome all open with the same frame. Prospects in discovery calls
repeat the positioning back in their own words within the first few
minutes — the most reliable signal that positioning has landed. Sales
close rate typically lifts within a quarter because the sales team is
no longer translating between three internal versions of "what we do."

The positioning statement becomes a decision filter for feature
prioritization too. A feature that strengthens the differentiation
clause clears the bar; one that drifts toward a different category or
ICP is deferred. Over time the statement fades into the background —
the team stops quoting it and just operates from it.

## Quality Gates

- Statement fits the template (ICP, category, value, alternatives,
  differentiation) without hand-waving on any clause.
- Five ICP-matching prospects paraphrase it back in their own words
  within a tolerable drift.
- Differentiation clause names something a well-funded copycat cannot
  replicate in one quarter.
- Homepage hero, sales deck opener, and onboarding welcome all reflect
  the same frame within two weeks of lock-in.

## Companion Integration

Invoked by Matilha core skills (`matilha-plan`) when market framing or
competitive framing is unclear. Pairs with `growth-jtbd-forces` (the
forces reveal the job being hired; positioning names that job in the
market frame) and with `growth-icp-definition` (narrower ICP makes
positioning sharper). Does not delegate to other packs in v0.1.0; no
direct `matilha-ux-pack` sibling at this strategic layer.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: one ICP, one category, one differentiation clause
  per statement; prospect-paraphrase validation before lock-in.
- Use "should" for: yearly review cadence; inclusion of non-obvious
  alternatives in the alternatives clause.
- Use "may" for: the specific phrasing and tone of the category noun —
  invented category names versus known ones.

## Troubleshooting

- **"The statement feels generic"**: The differentiation clause is
  weak. Push harder on what only the product can credibly claim —
  capability, data, community, or founder story.
- **"Prospects paraphrase it wrong"**: Either the category is unclear
  or the ICP is too broad. Narrow one and re-test.
- **"Sales still pitches differently"**: Ship a one-pager that shows
  the statement, the three proof points under each clause, and the
  banned alternative phrasings. Coherence beats elegance.
- **"The category name feels awkward"**: Invented categories always
  feel awkward at launch. If the category is described in the same
  words every competitor uses, the product has no positioning.

## Concrete Example

An email client competes in a crowded category. Broad positioning
("the best email app for teams") closes at a low rate against Gmail
and Outlook. The team runs switching-story interviews with 10 recent
paying users and finds a repeated Push: keyboard-only power users who
feel slowed by Gmail's mouse-driven UI. They reposition: "For
high-volume knowledge workers, Superhuman is the fastest email
experience that gets inbox-zero daily, unlike Gmail and Outlook
because every action is sub-100ms and keyboard-driven." ICP tightens
from "teams" to "individual power users." Pricing reinforces the
premium frame. Close rate within the narrowed ICP rises sharply;
mass-market volume drops, but revenue per user climbs. The team stops
chasing every feature request and ships only what reinforces the "fast
keyboard-first" frame.

## Sources

- `[[concepts/csv-brand-positioning]]`
- `[[concepts/jtbd-positioning]]`
- `[[sources/product-htrategy]]`
- Inspired by Al Ries & Jack Trout's "Positioning: The Battle for Your
  Mind," April Dunford's "Obviously Awesome," and Clayton Christensen's
  Jobs-to-be-Done framing, paraphrased through Danilo's wiki synthesis
  of positioning as a JTBD-anchored discipline rather than a
  feature-comparison exercise.
