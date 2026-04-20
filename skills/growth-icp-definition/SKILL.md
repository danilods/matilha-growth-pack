---
name: growth-icp-definition
description: Use when defining ideal customer profile — narrow ICP via JTBD plus firmographic plus behavioral filters for sharp targeting.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team needs to name who the product is actually for, with
enough specificity that messaging, sales targeting, pricing, and
feature work all point at the same people. Fires when sales close
rate is low and spread thin, when marketing copy drifts toward
everyone, or when feature requests come from segments that never pay
well. A well-defined ICP is the single artifact that resolves more
downstream arguments than any other strategy document.

## Preconditions

- The product has at least a handful of paying customers or deeply
  activated users whose behavior can be analyzed. ICP work from
  scratch, with no behavioral evidence, tends to produce TAM math
  rather than ICP.
- The team has access to basic firmographic data (company size,
  industry, tech stack) and behavioral data (feature usage,
  onboarding completion, retention) for existing customers.
- Leadership is willing to exclude segments. ICP definition that says
  "everyone in [huge industry]" is positioning theater, not ICP.

## Execution Workflow

1. Use Read on customer data, cohort retention reports, and CRM
   close-rate data. Segment the top 10% of customers by a composite
   of fastest onboarding, highest retention, and most referrals.
   This cohort is the empirical seed of the ICP.
2. Map the seed cohort across three lenses. JTBD — what job are they
   hiring the product to do, in their own words? Firmographic —
   company size, industry vertical, geography, tech stack, budget
   authority. Behavioral — what tool did they use before, how
   frequent was the pain, who inside the company championed the
   purchase?
3. Look for convergence. A strong ICP shows clustering on all three
   lenses — similar jobs, similar firmographics, similar behavioral
   signatures. Weak ICPs have wildly heterogeneous seed cohorts.
4. Write the ICP statement: "[firmographic description] who are
   currently [behavioral context] and need to [job statement]." Make
   it specific enough that a sales rep could disqualify a lead in one
   question.
5. Build the disqualification list — explicit anti-ICP signals that
   indicate a lead will close poorly or churn fast. Equal weight to
   the definition. Knowing who not to chase is half of ICP work.
6. Propagate to downstream artifacts. Sales qualification scripts,
   homepage hero headline, feature prioritization filter, pricing
   structure. An ICP that lives in one doc and nowhere else has no
   operational force.
7. Re-narrow every 12 months. As the product matures and the ICP
   expands, the early sharpness erodes unless actively re-examined.
   Horizontal products (Slack, Notion, Linear) start narrow and
   expand; the ICP shifts over time, and the team must track it.

## Rules: Do

- Start with past-winner behavioral evidence. The top 10% of existing
  customers reveal the ICP more reliably than market-sizing math.
- Define across three lenses (JTBD, firmographic, behavioral). Any
  one lens alone is thin; the three together triangulate sharply.
- Write a disqualification list alongside the ICP statement. Who is
  not the ICP matters as much as who is.
- Narrow harder than feels comfortable, especially for early and
  mid-stage products. "Everyone" serves no one well.
- Propagate the ICP into sales scripts, homepage copy, feature
  priority, and pricing structure. An undocumented ICP is noise.

## Rules: Don't

- Don't define ICP from TAM math ("there are 200K SMBs in
  [industry]"). Market size says nothing about whether those users
  buy or retain.
- Don't let every vocal customer shape the ICP. The loudest customers
  are often not the best fit; behavioral data is more honest than
  feedback.
- Don't write an ICP statement so broad that a sales rep cannot
  disqualify a lead. "B2B SaaS teams" is not an ICP.
- Don't conflate buyer persona with ICP. Buyer persona is the
  individual inside a company; ICP is the company or use-case.
- Don't freeze the ICP. Re-narrow every 12 months as evidence shifts.
  ICP drift is a leading indicator of positioning decay.

## Expected Behavior

After applying the skill, the team has a one-sentence ICP statement
that a new hire can recite after their first week. Sales rep close
rate inside the ICP lifts noticeably (often 2-3x); close rate outside
the ICP is explicitly deprioritized. Feature prioritization debates
shift from "users want this" to "does the ICP need this." Pricing
starts to align with ICP willingness-to-pay rather than
lowest-common-denominator anchoring.

Marketing copy sharpens because the hero headline can now reference
the ICP's specific pain in their own words. Onboarding tightens
because the team knows what the ICP walks in expecting. Over time,
the cohort retention curves flatten at higher levels as churning
mis-fits exit and ICP-fit users become the dominant mass.

## Quality Gates

- ICP statement fits the template (firmographic, behavioral context,
  job statement) and names specific enough detail that a new hire
  could disqualify a lead using it.
- Disqualification list exists and is at least as long as the
  definition list.
- The top-10% behavioral seed cohort shows convergence on all three
  lenses; if it doesn't, the ICP is still fragmented.
- Downstream artifacts (sales scripts, homepage hero, feature
  priority filter) reflect the ICP within one quarter of lock-in.
- Yearly review cadence is scheduled; ICP is not a one-time document.

## Companion Integration

Invoked by Matilha core skills (`matilha-plan`, `matilha-scout`) when
targeting or messaging decisions surface. Pairs with
`growth-jtbd-forces` (the JTBD lens of ICP comes from switching
stories) and with `growth-positioning-strategy` (narrow ICP makes
positioning sharper). Does not delegate to other packs in v0.1.0; no
direct `matilha-ux-pack` sibling at this strategic layer.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: three-lens definition (JTBD + firmographic +
  behavioral); disqualification list alongside the statement.
- Use "should" for: behavioral evidence from existing top-10% cohort;
  yearly re-narrow cadence.
- Use "may" for: the specific firmographic attributes emphasized
  (company size vs. industry vs. tech stack) — product-dependent.

## Troubleshooting

- **"The seed cohort doesn't cluster"**: Either the product is still
  finding PMF (too early for ICP work) or the cohort is too small.
  Expand to top 20% and retest; if still no cluster, focus on JTBD
  interviews before revisiting ICP.
- **"ICP feels too narrow to hit revenue targets"**: Either the
  narrow ICP is too small a market (reconsider product strategy) or
  the team is confusing ICP with TAM. Narrow ICP is the wedge; the
  market expands after the wedge wins.
- **"Sales ignores the ICP"**: ICP is not operationalized. Ship a
  one-pager that lists qualifying questions, disqualifying signals,
  and example accounts.
- **"The ICP drifts every quarter"**: Review cadence is too frequent.
  ICP should be stable for ~12 months; quarterly rewriting indicates
  underlying PMF instability.

## Concrete Example

A CRM product starts with "all small businesses" as its target. Sales
close rate sits at 3%, onboarding completion is low, and churn is
high. The team pulls the top 10% of retained customers and finds
convergence: 5-50 person B2B services firms, Gmail power users,
specifically struggling with client follow-ups falling through email
threads. The ICP tightens to "5-50 person B2B services firms using
Gmail who are losing client follow-ups in email threads." Hero
headline shifts from "A better CRM" to "Stop losing Gmail threads with
clients." Sales close rate inside the ICP rises to 18%; outside the
ICP it drops but is explicitly deprioritized. Onboarding tightens
because the team knows the ICP's workflow. Eighteen months later the
team widens to adjacent ICPs from a position of strength, rather than
drowning in generic positioning from the start.

## Sources

- `[[concepts/jtbd-positioning]]`
- `[[sources/product-htrategy]]`
- Inspired by April Dunford's "Obviously Awesome" ICP framing and
  Bob Moesta's JTBD switching-story work, paraphrased through
  Danilo's wiki synthesis of ICP as a three-lens behavioral artifact
  rather than a TAM-math exercise.
