---
name: growth-activation-aha-moment
description: Use when designing onboarding — identify and accelerate users reaching the aha moment before churn window closes.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a product has sign-ups but losing users in the first days, when
an onboarding flow has been built by opinion rather than evidence, or
when the team cannot agree on what "activated" means. Fires before a
retention intervention is attempted, because retention work on
unactivated users is wasted effort. The skill derives the aha moment
from cohort data and redesigns the first-session path to push users
toward it fast.

## Preconditions

- At least a few weeks of user behavior exist; cohort comparison needs a
  retention window to compare against.
- Event instrumentation captures the actions a user could plausibly take
  in week one (creating, inviting, saving, publishing, etc.).
- The team accepts that the aha moment will be derived from data, not
  chosen by opinion.

## Execution Workflow

1. Use Read or the analytics tool to pull the user cohort from eight to
   twelve weeks ago — old enough to have a credible D30 retention signal,
   recent enough to reflect current product shape.
2. For each candidate action in week one (created-a-project, invited-a-
   teammate, saved-a-file, published-content, completed-profile), split
   the cohort into users who did the action and users who did not.
   Compute D30 retention for each split.
3. Find the action with the widest retention gap between did and did-not.
   The candidate that produces, say, sixty percent D30 retention for
   doers and eight percent for non-doers is a strong aha-moment signal.
   A gap under a factor of two is weak — keep looking or combine
   actions.
4. Refine to a quantified form. "Created a project" is a direction;
   "created two projects in week one" is an aha moment. Sweep the
   threshold and pick the smallest amount that produces the retention
   lift — forcing more than necessary hurts activation rate.
5. Confirm the aha moment is product-plausible. It should correspond to
   a moment where the user could reasonably say "oh, I see why this
   helps me." A statistical artifact that does not make product sense
   usually reflects a confounder (e.g. already-loyal users do the
   action, not the action producing loyalty).
6. Redesign the first session to push users toward the aha action.
   Prefer product mechanisms over email: sample data, templates,
   empty-state prompts, a guided path that makes the first aha action
   the obvious next step. Email nudges fill in day-two and day-three
   gaps.
7. Use Edit to remove or defer steps that do not contribute to the aha
   path. Every friction between sign-up and the aha moment costs
   activation rate. Profile completion, tour tours, and "meet the team"
   screens are usually deletable.
8. Re-measure activation rate after two weeks and confirm the aha-moment
   definition still holds; product changes can move the threshold over
   time.

## Rules: Do

- Derive the aha moment from cohort retention data, not from a workshop
  whiteboard.
- Quantify it: a number of actions in a time window, not a vague
  "engaged with the product."
- Redesign onboarding to make the aha action the shortest path from
  sign-up, not a buried option.
- Respect the churn window; for most productivity tools it is roughly
  seven days. Social products are shorter, utilities longer. Time the
  push accordingly.
- Treat activation rate as the leading metric of retention — a change
  here appears in retention dashboards weeks later.

## Rules: Don't

- Don't confuse sign-up with activation; sign-up is an input, activation
  is the first-value moment the user feels.
- Don't pick an aha moment because stakeholders like it; if the data
  disagrees, the data wins.
- Don't load the first session with non-aha work (full profile, payment
  method capture, long tutorials) — every screen before aha costs
  percentage points.
- Don't gate the aha moment behind payment or an invite acceptance;
  users churn before they hit the wall.
- Don't change the aha-moment definition mid-experiment; lock it for the
  measurement window.

## Expected Behavior

After applying the skill, the team has a one-sentence definition of
activation that everyone uses. Product decisions get clearer: a feature
pitch either makes the aha action easier to reach or does not. Marketing
can brief the ad creative on the aha moment, not on vague "benefits."
Support can see that users who bounce did not reach activation and
intervene upstream instead of chasing retention downstream.

Activation rate becomes the weekly conversation. When it moves, the team
knows within two weeks because they are watching it specifically. When
it does not move, the team can point at exactly which step between
sign-up and the aha action is breaking, because the first session has
been trimmed to that path.

## Quality Gates

- Activation is defined as a quantified action in a time window, not as
  a fuzzy concept.
- The aha moment has a retention-gap ratio of at least roughly two to
  one between users who did and did not perform it.
- The first-session flow has been audited and every non-aha step is
  justified or removed.
- A churn-window assumption is written down and reflected in the push
  mechanism (immediate, day-one, day-two).
- Activation rate is reported weekly and owned by a named person.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
onboarding or activation decisions surface. Runs downstream of
`growth-aarrr-funnel` (which often names Activation as the weakest
stage) and pairs with `growth-jtbd-forces` (aha moments are usually
where Pull meets absence of Anxiety). Does not delegate to other packs
in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: data-derived aha-moment definition, quantification as
  an action-in-a-window.
- Use "should" for: first-session trimming to the aha path, weekly
  activation-rate reporting.
- Use "may" for: specific thresholds (number of actions, window length),
  which are product-dependent.

## Troubleshooting

- **"The retention gap is only 1.3x"**: The candidate is weak. Try a
  combination (created-a-project AND invited-a-teammate) or move the
  threshold (two actions instead of one). If no candidate passes 2x,
  the product may lack a genuine aha moment and the retention problem
  is deeper than onboarding.
- **"Activation rate moved but D30 retention did not"**: Either the aha
  moment is an artifact (confound rather than cause), or the retention
  measurement is too soon. Re-measure at D30 once the activated cohort
  has aged.
- **"Leadership wants to add a profile-completion step"**: Ask how much
  it moves the aha path. If it delays the aha action by more than a
  minute, it almost certainly costs more activation than it gains in
  downstream engagement.
- **"Support says users don't understand the product"**: That is a
  pre-aha problem. Do not answer it with more help content; answer it
  by getting users to the aha action faster so the product explains
  itself.

## Concrete Example

A design tool runs cohort analysis across eight candidate week-one
actions. The widest retention gap lands on "created two or more
designs in the first seven days": doers show roughly sixty percent D30
retention, non-doers show eight percent. Sign-up flow is trimmed — the
profile screen moves to post-activation, the video tour becomes
dismissible, and a first-session prompt offers one of four template
duplications that produce a design in under two minutes. A day-two
email nudges a single template tweak to produce design number two.
Activation rate (two designs in week one) climbs from twenty-three to
forty-seven percent over the next month, and D30 retention on the new
cohort lands roughly where the model predicted.

## Sources

- `[[concepts/plg-estrategias-growth]]`
- `[[concepts/aarrr-growth-metrics]]`
- `[[sources/product-growth-hacking]]`
- Inspired by the aha-moment literature from Facebook, Twitter, and
  Dropbox growth teams, paraphrased further through Danilo's wiki
  synthesis of cohort analysis and onboarding patterns.
