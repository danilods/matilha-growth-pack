---
name: growth-peak-end-journey
description: Use when designing session or journey-level satisfaction — apply Peak-End rule to memory-of-experience design, prioritizing emotional peaks and endings.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when the team is deciding which moments in a session or journey
to invest in — not which UI element to polish, but which overall
experience beats to amplify. Fires when user satisfaction surveys
conflict with objective session metrics (short sessions score well,
long sessions score poorly, or vice versa), when return rates lag
engagement, or when the team is designing a multi-step flow
(onboarding, checkout, cancellation, a workout, a campaign) where
the average moment matters less than the peaks and the ending.

## Preconditions

- The team can identify a bounded journey or session — onboarding
  flow, single workout, weekly planning ritual, campaign send
  sequence, cancellation flow. Peak-End analysis on unbounded
  "everything the user does" is noise.
- There is qualitative or quantitative signal about which moments
  users remember — NPS open-text, session-end surveys, retention
  cohorts segmented by last-action-type. Designing peaks without
  memory evidence is speculation.
- Leadership accepts that average-moment optimization is an inferior
  frame. Peak-End implies deliberate unevenness: tolerate mediocre
  middles, invest in peaks and endings.

## Execution Workflow

1. Use Read on user feedback corpora, NPS open-text, retention data
   segmented by last-action-in-session, and cancellation-survey
   responses. Identify the bounded journey under study.
2. Map the journey's emotional curve. Walk through the moments from
   start to end and rate each for emotional valence (high/neutral/
   low) and user memorability. Duration neglect means long boring
   middles score neutral and can be tolerated; sharp peaks and
   endings dominate recall.
3. Identify the current peak. Is it positive or negative? In many
   products the unintentional peak is negative — a failure state, a
   slow load, a confusing step. Negative peaks dominate memory even
   when the rest of the journey is fine.
4. Identify the current ending. The final 5-30 seconds of a session
   bias the entire recall. Common bad endings: loading screens, error
   states, silent logouts, bitter cancellation flows. Common good
   endings: accomplishment summaries, forward-looking teasers,
   genuine gratitude, signature moments.
5. Engineer one deliberate positive peak. Pick a single moment where
   a surprise, celebration, or delight can land. Resist the urge to
   spread investment evenly across the journey — one strong peak
   beats five mild ones.
6. Engineer the ending deliberately. Four patterns work: session
   summary ("today you did X, Y, Z"), encouragement ("great work, 3
   days of streak"), teaser ("tomorrow, check out the new feature"),
   genuine gratitude. Even cancellation flows benefit from a
   non-bitter ending — the user may return.
7. Eliminate the worst negative peak before investing in positive
   peaks. A single painful moment dominates memory regardless of how
   good the peaks are. Negative-peak elimination is higher leverage
   than positive-peak addition.
8. Instrument. Track last-action-in-session distribution,
   next-session return rate by ending type, and NPS text mentions of
   specific moments. The peak and ending should become observable in
   the data within a release cycle.

## Rules: Do

- Operate at session or journey level — which moments to amplify,
  which to end strongly — rather than at individual UI moment tone
  and copy.
- Eliminate the worst negative peak before investing in positive
  peaks. Negative peaks dominate memory asymmetrically.
- Engineer one strong positive peak, not many mild ones. Peak
  memorability is nonlinear; the brightest moment anchors recall.
- Engineer the ending deliberately. The final 5-30 seconds bias the
  entire recall of the session.
- Tolerate mediocre middles. Duration neglect means boring stretches
  score near-neutral and are not where investment compounds.

## Rules: Don't

- Don't spread polish investment evenly across every moment. Peak-End
  implies deliberate unevenness.
- Don't end sessions on errors, loading screens, or silent logouts.
  The last impression biases everything.
- Don't make cancellation flows bitter. The user who cancels today
  may return next quarter; a bitter ending closes the door.
- Don't conflate Peak-End with UI-moment tone. This skill operates at
  journey scale — which moments to amplify; UI-moment tone lives at
  feature level.
- Don't optimize average session quality as a primary metric. Average
  is a weak predictor of memory; peaks and endings are the stronger
  signal.

## Expected Behavior

After applying the skill, the team has a journey map with explicit
peaks and endings, not a uniform quality curve. User satisfaction
surveys climb without proportional investment in average-moment
polish, because the moments that drive memory now carry the journey.
Return rates improve as endings shift from "silent logout" or
"loading spinner" to "accomplishment summary" or "forward-looking
teaser." Cancellation flows generate some return customers months
later because the ending was not bitter.

Internally, the team stops arguing about which micro-moment to
polish next and starts asking "what is the peak, and what is the
ending." Unimportant middles get less investment, freeing resources
for the 1-2 moments that actually bias memory. Over time, signature
peaks become word-of-mouth moments — what users tell their friends
about is almost always the peak, rarely the average.

## Quality Gates

- A bounded journey is identified; Peak-End analysis is not applied
  to "everything the user does."
- The current peak and ending are named and classified as positive,
  neutral, or negative, with evidence.
- The worst negative peak, if any, is prioritized for elimination
  before positive-peak investment.
- One deliberate positive peak and one deliberately engineered
  ending are shipped and instrumented.
- Last-action-in-session distribution and next-session return rate
  are tracked by ending type.

## Companion Integration

Complements `matilha-ux-pack:ux-emotion-in-ui` which treats tone/copy at individual UI moment. This skill operates at entire session/journey level: which moments to amplify (peaks), how to end (endings).

Invoked by Matilha core skills (`matilha-plan`) when journey-level
experience design decisions surface. Pairs with
`growth-activation-aha-moment` (the aha moment is often the first
deliberate peak in the onboarding journey) and with
`growth-octalysis-drives` (Core Drives land most strongly at peaks
and endings).

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: bounded-journey definition; explicit peak and
  ending classification with evidence; negative-peak elimination
  before positive-peak investment.
- Use "should" for: one strong positive peak rather than many mild
  ones; ending-type instrumentation in analytics.
- Use "may" for: the specific ending pattern chosen (summary,
  encouragement, teaser, gratitude) — journey-dependent.

## Troubleshooting

- **"We added a peak but satisfaction didn't move"**: Check whether a
  negative peak still dominates. Elimination always outranks
  addition.
- **"Users mention the bug, not the peak"**: Same failure mode. A
  single painful moment dominates recall regardless of how strong the
  positive peak is.
- **"Return rate didn't change after ending redesign"**: Instrument
  by ending type — the redesign may not be firing at the right
  moment in the session, or users are terminating sessions earlier
  than the new ending triggers.
- **"We can't find the peak"**: Run NPS open-text analysis — users
  self-report peaks unprompted. If no moment emerges, the journey may
  not yet have a peak to amplify; build one deliberately.

## Concrete Example

A video-editing SaaS reviews user satisfaction data. Users rate the
overall product highly but return less frequently than engagement
would predict. Peak-End analysis shows the ending of a session is
almost always "export wait" — a 30-60 second progress bar followed
by a silent save-to-disk. The team redesigns the export completion
screen: a celebratory animation, a one-line summary ("Ready!
3-minute video, 60% faster than your average export"), and three
forward-looking CTAs (share, edit again, start new project). The
last 5 seconds of the session shift from "waiting" to
"accomplishment." User satisfaction surveys climb within a release
cycle; return rate improves noticeably despite no change in actual
export speed. The peak (still the first successful playback of the
edited video) was already fine; the ending was the leverage.

## Sources

- `[[concepts/peak-end-rule]]`
- `[[sources/product-htrategy]]`
- Inspired by Daniel Kahneman's "Thinking, Fast and Slow" and his
  "When More Pain Is Preferred to Less" paper on the Peak-End rule,
  paraphrased through Danilo's wiki synthesis of Peak-End at
  session/journey level rather than at individual UI-moment tone
  level.
