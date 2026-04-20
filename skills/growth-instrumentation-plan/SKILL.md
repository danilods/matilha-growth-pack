---
name: growth-instrumentation-plan
description: Use when instrumenting a product for growth measurement — map events to AARRR stages and value-driving actions before writing tracking code.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when an engineering team is about to add analytics tracking, a product
team is drowning in noisy dashboards, or a data team cannot answer basic
funnel questions because the events they have do not compose into rates.
Fires before any tracking code is written, not after. The skill names the
handful of semantic events that AARRR needs, defines their shape, and
closes the door on ad-hoc "just track every click" instrumentation.

## Preconditions

- The team has picked or is picking a North Star and roughly knows the
  AARRR stages relevant to the product.
- A value moment — the action that makes users say the product worked —
  is either named or can be named during this work.
- The analytics destination is chosen (or at least narrowed) so property
  shapes match the destination's constraints.

## Execution Workflow

1. Use Read on existing analytics code, if any, to catalogue what already
   fires. Expect to find far more events than are useful and far fewer
   that map to AARRR stages cleanly.
2. For each AARRR stage, list two or three semantic events that answer
   "did the user do the thing that matters here?" Acquisition: visit a
   landing page or start a sign-up. Activation: complete a first-value
   action. Retention: repeat the value action inside a cohort window.
   Revenue: upgrade or pay. Referral: send an invite and have an invite
   accepted.
3. Name events by verb-plus-object, not by UI element. "project_created"
   survives a redesign; "btn_click_newproj_blue" does not. The event name
   should read like a sentence about user intent.
4. Define the shared property set that every event carries. User id, plan
   tier, session id, experiment-variant map, platform, and a stable
   client-side timestamp. These turn single events into cohort-analyzable
   data.
5. Define per-event properties that answer the "which kind" question.
   A project-created event carries project type and template used. An
   invite-sent event carries channel, recipient count, and whether a
   message was added. Properties replace the temptation to create ten
   variants of the same event.
6. Version the spec. Put it in a file (YAML, Markdown, or a typed schema)
   checked into the repo with a version number. Event-shape drift breaks
   dashboards silently; versioning makes the breakage loud and
   localizable.
7. Use Edit or Write to commit the spec before instrumentation starts.
   Engineering writes tracking calls against the spec, not against
   feelings. Dashboards and queries are written against the spec names,
   not against whatever-showed-up-in-the-destination.
8. Build a privacy pass. Strip raw PII from properties; hash identifiers
   that must persist; check that free-text fields cannot leak form input.
   Privacy review at spec time is ten times cheaper than post-launch.

## Rules: Do

- Instrument the user's intent, not the DOM. Rename every click-on-button
  event to the action it represents.
- Limit yourself to roughly eight to fifteen semantic events across the
  whole AARRR funnel. More than that and the spec is tracking
  implementation detail.
- Attach the common property set to every event so cohort and experiment
  cuts work without joins.
- Put the spec in version control and treat changes as API changes —
  reviewed, versioned, and announced.
- Handle identity early. Pick one user-id strategy (anonymous vs
  authenticated, alias on sign-up) and stick to it across platforms.

## Rules: Don't

- Don't add events reactively one-by-one when a dashboard request comes
  in; the spec is the list, the destination is the consequence.
- Don't name events after UI components; UIs change, intent does not.
- Don't ship raw PII into the analytics destination under any name
  ("user_email" is still PII no matter where it lives).
- Don't let two teams instrument the same intent under two names; the
  dashboard will report the sum of the two events plus zero, and nobody
  will notice.
- Don't instrument "every page view" as the foundation of the plan; page
  views are sampling noise unless a page corresponds to an AARRR event.

## Expected Behavior

After applying the skill, the tracking layer becomes small, legible, and
stable. A new analyst reads the spec and can write a funnel query the
same day. Dashboards built from the spec survive front-end refactors
because event names encode intent, not markup. Product and growth teams
converge on the same numbers because they are querying the same
small event set.

Experiments become straightforward. The experiment-variant property on
every event means any event can be cut by test group without custom
instrumentation per test. Privacy review becomes a routine pass rather
than a project, because PII never enters the pipeline in the first
place.

## Quality Gates

- The spec lists no more than roughly fifteen semantic events, each tied
  to an AARRR stage or explicitly flagged as operational.
- Every event name is verb-plus-object and survives a hypothetical UI
  rewrite.
- A common property set covers user id, plan tier, session id, and
  experiment variants on every event.
- The spec is versioned, stored in the repository, and referenced by
  instrumentation code.
- Privacy review confirms no raw PII flows to the destination.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
measurement decisions surface. Runs after `growth-aarrr-funnel` (to know
which stages exist) and `growth-north-star-metric` (to know which events
feed the growth equation). Hands off to engineering for implementation;
the spec is the contract. Does not delegate to other packs in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: semantic event names, the common property set, privacy
  pass before launch.
- Use "should" for: two-to-three events per AARRR stage, versioned spec
  file.
- Use "may" for: the specific analytics destination, property-shape
  conventions beyond the required common set.

## Troubleshooting

- **"We already track 300 events and dashboards are still broken"**: The
  fix is not to track more, it is to track less. Build the fifteen-event
  AARRR spec, migrate dashboards to it, and turn off or ignore the old
  events rather than racing them.
- **"Events fire but user counts don't match the backend"**: Identity is
  almost always the culprit. Audit the alias call on sign-up and verify
  that anonymous-to-authenticated transitions carry the anonymous id
  forward.
- **"A feature shipped and nobody instrumented it"**: Instrumentation
  should be part of the definition of done. Add a spec-update checklist
  item to the PR template.
- **"Dashboards keep breaking after redesigns"**: Event names still
  encode UI. Rename to verb-plus-object and grandfather the old names
  with a deprecation window.

## Concrete Example

A team instruments "page_view" on every screen plus a button-click event
for every CTA, ending up with roughly two hundred event names after a
year. Growth questions take days to answer because composing rates
requires complex joins and deduplication. The plan is redrawn around
eight semantic events: signup_started, signup_completed,
first_project_created, first_collaborator_added, return_after_7d,
invite_sent, invite_accepted, subscription_paid. Each event carries the
common property set plus event-specific properties. The AARRR dashboard
now composes from the eight events without any ETL, the experiment
pipeline reuses the variant property on every event, and the team
retires the old instrumentation over a quarter with no dashboards lost.

## Sources

- `[[concepts/aarrr-growth-metrics]]`
- `[[sources/product-growth-hacking]]`
- Inspired by Dave McClure's AARRR framing and industry instrumentation
  practice, paraphrased further through Danilo's wiki synthesis of
  event-naming and cohort-property conventions.
