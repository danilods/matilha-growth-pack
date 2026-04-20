---
name: growth-category-creation
description: Use when creating a new market category — apply category-design principles to dominate rather than compete in existing categories.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team has a missionary insight — a view of a problem the
market has not yet named, and a product that reframes how people
should think about that problem. Fires when positioning inside an
existing category feels constraining, when competitors are shouting
feature comparisons that miss the point, or when the founder keeps
saying "we are not really a [known category], we are something new."
This skill helps the team decide whether category creation is viable,
and if so, how to invest in it coherently over multi-year horizons.

## Preconditions

- The team can articulate a problem frame that existing categories
  mislabel or hide. Category creation requires missionary conviction,
  not contrarianism for its own sake.
- The addressable market is large enough to support a dominant
  category king. Play Bigger's research suggests the category king
  captures most of the economic value in a new category — a small
  category yields a small prize.
- Leadership accepts a multi-year investment in category marketing,
  conferences, thought leadership, and practitioner identity, not a
  quarterly ROI target.

## Execution Workflow

1. Use Read on the team's strategic docs, user interviews, and
   industry press. Identify phrasing gaps — where do users
   consistently describe the problem in awkward, product-suffix ways
   ("the thing that does X plus Y")? Awkward language signals a
   missing category.
2. Draft 3 candidate category names. Each should be a noun phrase
   that evokes the new frame, typically 2-3 words, and anchored on
   the user's problem rather than the product's internal architecture.
   "Sales engagement platform" anchors on user; "AI-powered email
   sequencer" anchors on feature — choose the former.
3. Stress-test against the "should we create a category" filter. If
   the market is mature with an established king, if the TAM is
   small, or if users already have a shared vocabulary for the
   problem, category creation is the wrong move. Use
   `growth-positioning-strategy` inside the existing category
   instead.
4. Build the category narrative. Write the problem manifesto — why
   this problem matters now, why existing categories fail it, what
   the future looks like when the category is served well. This
   document is the anchor for every downstream asset.
5. Invest in language. Every blog post, sales call, and investor
   pitch uses the new category name. Retrain the team to stop
   describing the product in the old category's terms; language
   consistency is category enforcement.
6. Define the practitioner identity. What job title emerges as the
   buyer and user inside the category? Invest in that identity —
   conferences, certifications, communities, career playbooks. Owning
   the practitioner is owning the category.
7. Ship the category, not just the product. Publish books, host
   conferences, invent benchmarks. Category marketing comes first;
   direct response sales pressure second. Competitors who enter later
   will do so on the framework the pioneer built.
8. Monitor the category king signal. Within 18-36 months, is the team
   cited as the pioneer in analyst reports, in practitioner
   communities, in press? If not, the category is not taking — either
   double down or reposition into an existing category before the
   window closes.

## Rules: Do

- Name the category with a noun phrase anchored on the user's problem,
  not the product's architecture or features.
- Publish the problem manifesto before polishing the product page —
  the narrative layer precedes the marketing layer.
- Invest in practitioner identity (job title, community, career
  path). Owning the practitioner is the durable moat.
- Run a consistent multi-year category investment. Quarterly
  direct-response thinking cannibalizes category creation.
- Make competitors answer the frame. When a rival publishes content
  using the new category language, the category is taking hold.

## Rules: Don't

- Don't create a category in a mature market with an established king.
  Second-to-category loses; use `growth-positioning-strategy` to carve
  a subcategory instead.
- Don't invent category jargon for existing problems with clear
  vocabulary. Users will reject the rebranding and buy from the
  plainspoken competitor.
- Don't let the sales team default to old-category language. Every
  customer call is either category reinforcement or category erosion.
- Don't measure category creation with short-window conversion
  metrics. Measure with share-of-voice, analyst coverage,
  practitioner adoption of the category term.
- Don't confuse category creation with feature positioning. Adding
  "AI" to the product description is not inventing a category.

## Expected Behavior

After applying the skill, the team speaks one language across every
touchpoint — analysts, prospects, employees, investors. Over 12-24
months, industry press starts using the category name unprompted.
Competitors enter the market and adopt the framing, which looks like
a threat but is actually validation that the category exists. The
team's narrative, not its feature list, becomes the reason prospects
buy. Sales cycles often shorten because the category frame does the
first-meeting work before the sales rep opens the call.

Internally, hiring becomes clearer — job descriptions reference the
category, candidates self-select. Roadmap debates shift from
"what feature do we ship" to "what does a true [category] product
need to do" — a structurally stronger question.

## Quality Gates

- Category name passes the user-paraphrase test: three ICP prospects
  use the term naturally within one month of first exposure.
- Problem manifesto exists as a published document and anchors all
  downstream content.
- The team has named the target practitioner identity and invested
  in at least one channel (conference, certification, community).
- Competitors or analysts begin using the category term within 12-18
  months; absence of this signal by month 24 triggers a re-evaluation.

## Companion Integration

Invoked by Matilha core skills (`matilha-plan`) when the team's
framing feels constrained by existing categories. Pairs with
`growth-positioning-strategy` (category creation is positioning's
more ambitious cousin — use positioning when category creation is not
viable) and with `growth-icp-definition` (category creation needs a
sharply defined practitioner identity). Does not delegate to other
packs in v0.1.0; no direct `matilha-ux-pack` sibling at this strategic
layer.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: noun-phrase category name anchored on user problem;
  published problem manifesto before product-page polish.
- Use "should" for: multi-year investment horizon; practitioner
  identity investment in at least one channel.
- Use "may" for: the specific mix of books, conferences, benchmarks,
  and communities used to enforce the category.

## Troubleshooting

- **"The category name feels made-up"**: Invented categories always
  feel awkward for the first year. If the team is not slightly
  embarrassed by the name, it is probably generic.
- **"Users don't understand the new term"**: Either the term is too
  abstract or the problem manifesto has not circulated. Publish the
  manifesto and retest.
- **"Sales keeps defaulting to old category language"**: Category
  enforcement is a training problem. Ship a one-pager that shows
  old-category phrasings and their new-category rewrites.
- **"A competitor claimed the category first"**: Either win the
  category war by out-investing (rare and expensive), or reposition
  into a subcategory. Second-to-category almost never wins.

## Concrete Example

A CS-ops team around 2010 saw a pattern: B2B SaaS companies were
hiring "account managers" to keep customers renewing, but the role
felt misnamed — these people were not really salespeople and not
really support. The founder called the job "customer success
manager" and named the category "Customer Success." For years the
team wrote books, ran the Pulse conference, funded certifications,
and shipped a tool (Gainsight) that only made sense inside the new
frame. Competitors entered but had to speak the language the
pioneer had built. Contrast: a team adds "AI-powered" to an existing
HR-tech product and calls it a new category. Nothing new is actually
framed — that is feature positioning, not category creation, and the
market ignores the rebrand.

## Sources

- `[[concepts/csv-brand-positioning]]`
- `[[sources/product-htrategy]]`
- Inspired by Al Ries' category positioning principles and Play
  Bigger's "Play Bigger: How Pioneers, Innovators, and Category
  Kings Create and Dominate Markets," paraphrased through Danilo's
  wiki synthesis of category creation as a multi-year narrative
  investment rather than a launch event.
