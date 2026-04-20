---
name: growth-hook-model-product
description: Use when designing product-level habit formation — apply Hook Model (trigger, action, variable reward, investment) to strategic user flows with ethical guardrails.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when the team is deciding whether the product should form a habit,
which journeys should form habits, and how to architect the loops at
product-flow level. Fires when retention curves flatten too early,
when the team debates "should we add notifications," or when a new
product category is unclear on its expected cadence (daily, weekly,
monthly). This skill operates at strategic product-flow level — which
user journeys deserve habit-loop investment, which should not —
rather than at feature-level engagement mechanic design.

## Preconditions

- The product has at least one journey with observable cadence in
  real user data. Designing habit loops with no behavioral baseline is
  speculation.
- The team has capacity to ship loop interventions (triggers,
  variable rewards, investment surfaces) over a 6-12 week horizon —
  habit loops need 4+ user cycles through the loop to form, which
  takes real calendar time.
- Leadership accepts the ethical filter. Products that form habits
  the user would not endorse if they saw the mechanics erode trust
  over time; the team must explicitly reject "time well spent"-hostile
  designs.

## Execution Workflow

1. Use Read on product analytics, especially session cadence histograms
   and cohort retention curves. Identify which journeys show natural
   repeat behavior (daily-use utility, weekly-planning workflow) and
   which do not (annual tax tool, one-time onboarding).
2. Apply the ethical filter first. For each candidate habit journey,
   ask: does the user's goal align with forming this habit? A
   language-learning streak aligns; an infinite-scroll feed often does
   not. If the habit serves only the product's KPIs, stop.
3. Choose journeys worth habit investment. Habit loops are expensive
   — product-flow design, trigger infrastructure, reward
   instrumentation. Not every journey deserves one. Pick 1-2 core
   loops and ignore the rest.
4. Map each journey to the 4-stage Hook. Trigger (external: push
   notification, email, calendar integration; internal: emotional
   cue, context). Action (simplest behavior in anticipation of
   reward). Variable Reward (tribe/hunt/self — which variety fits the
   journey?). Investment (data, content, skill, or reputation the
   user deposits that improves next-loop experience).
5. Decide first-trigger strategy. Where does the habit loop enter the
   user's life? Push notification works for consumer; calendar
   integration works for B2B; email-to-inbox works for async work
   tools. Match trigger channel to ICP context.
6. Design the investment slot deliberately. Investment is the
   often-skipped stage that turns one-time reward into a loop —
   something the user deposits that makes tomorrow's session better.
   Without investment, the loop decays after novelty fades.
7. Instrument the loop. Track cycles-per-user-per-week and time-to-4th-
   cycle; 4+ cycles within a short window is the empirical signal
   that a habit is forming.
8. Ship off-ramps. For every habit loop the product creates, design
   a clear off-ramp — pause, mute, graceful churn. Users whose
   context has changed deserve respectful exits; refusing to offer
   them breaks the ethical contract and creates toxic goodwill.

## Rules: Do

- Apply the ethical filter before the mechanical filter. Ask "does
  this habit serve the user's stated goal?" before asking "can we
  build this loop?"
- Operate at product-flow level — which journeys should form habits —
  rather than at feature-level mechanics.
- Design investment deliberately. A loop without an investment slot
  decays after the novelty of the variable reward fades.
- Match first-trigger channel to ICP context (push for consumer,
  calendar for B2B, email for async work tools).
- Ship off-ramps for every habit loop. Pause, mute, graceful churn.
  The off-ramp is the honesty test of the loop.

## Rules: Don't

- Don't build habit loops on journeys where the user goal does not
  align with forming the habit. Infinite-scroll mechanics without a
  user win state fail the ethical test.
- Don't skip the investment stage. A trigger-action-reward loop
  without investment is a slot machine, not a habit.
- Don't measure habit formation by engagement alone. Engagement can
  rise while user wellbeing falls; measure retention-with-consent.
- Don't deploy habit mechanics without off-ramps. Users whose context
  changes must have respectful exits.
- Don't treat every journey as a habit candidate. Most journeys
  should not form habits; pick 1-2 core loops and invest deeply.

## Expected Behavior

After applying the skill, the team knows which product flows deserve
habit-loop investment and which do not. Retention curves inside the
targeted journeys flatten at higher levels within 8-12 weeks, as
users cycle 4+ times through the loop and habit formation takes hold.
The team has a clear answer to "should we add notifications" — yes
for the journeys that passed the ethical and strategic filters, no
for the rest.

Internally, debates shift from "how do we boost engagement" to "does
this loop serve the user's goal." Product-flow decisions — where the
loop lives in the product, how the first trigger enters the user's
life, what the investment slot looks like — become explicit design
questions with accountable owners. Ethical guardrails stop feeling
like a tax and start shaping which journeys get built at all.

## Quality Gates

- Each targeted habit journey passes the ethical filter with an
  explicit user-goal alignment statement.
- Each loop maps to all 4 Hook stages, including a concrete
  investment slot.
- First-trigger channel matches ICP context and is documented, not
  defaulted.
- Off-ramps exist for each loop and are discoverable by users
  without friction.
- Instrumentation tracks cycles-per-user-per-week and
  time-to-4th-cycle for the targeted journeys.

## Companion Integration

Complements `matilha-ux-pack:ux-variable-rewards` which applies Hook
Model at feature-level engagement mechanic design. This skill treats
Hook Model at strategic product-flow level.

Invoked by Matilha core skills (`matilha-plan`) when retention or
engagement strategy is under discussion. Pairs with
`growth-fogg-bmap-feasibility` (Fogg's B=MAP checks whether the
Action stage is feasible at all) and with `growth-activation-aha-moment`
(the aha moment is often the first variable reward in the loop).

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: ethical filter applied before mechanical design;
  investment stage concretely specified per loop; off-ramps shipped.
- Use "should" for: 1-2 core loops rather than many; 4+ cycles in
  short window as habit-formation threshold.
- Use "may" for: the specific first-trigger channel, reward variety
  (tribe/hunt/self), and investment surface — product-dependent.

## Troubleshooting

- **"Users cycle through the loop a few times then drop"**: The
  investment slot is missing or weak. Without investment, the loop
  decays after novelty. Add a deposit surface.
- **"Engagement rose but retention fell"**: The loop passed the
  mechanical test but failed the ethical test. Users are hooked
  short-term and churning medium-term. Reassess user-goal alignment.
- **"We can't figure out the internal trigger"**: Run a qualitative
  study — ask users what they were feeling or doing just before they
  opened the product. Internal triggers are emotional or contextual
  cues, not rational ones.
- **"The off-ramp reduces retention"**: Off-ramps should reduce
  retention of users whose context has changed. That is a feature,
  not a bug — those users return later when context shifts back.

## Concrete Example

A fitness app is designing its core habit loop. The ethical filter
passes — users explicitly want a fitness habit, and alignment holds.
The team maps the loop. Trigger: push notification at the user-set
workout time, plus the internal trigger of "I said I'd work out
today." Action: tap to start workout (sub-3-second friction).
Variable Reward: streak celebration (self), new workout variety
(hunt), occasional community shout-outs (tribe). Investment: user
logs completion plus rates the workout, which tunes tomorrow's
recommendation. Critically, the team also celebrates "rest days
planned," not just workouts completed — signaling user wellbeing is
the win state. Off-ramp: pause-streak-for-injury flow is one tap.
Contrast: a social feed with infinite scroll uses the same Hook
mechanics but has no user-goal alignment and no investment slot
beyond time spent — same machinery, opposite outcome for the user.

## Sources

- `[[concepts/hook-model]]`
- `[[concepts/dopamina-comportamento]]`
- `[[sources/product-htrategy]]`
- Inspired by Nir Eyal's "Hooked" and its ethical counterpart
  "Indistractable," and by Tristan Harris's "time well spent" frame,
  paraphrased through Danilo's wiki synthesis of Hook Model at
  product-flow level rather than feature-mechanic level.
