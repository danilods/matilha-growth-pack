---
name: growth-jtbd-forces
description: Use when researching user motivation — map Moesta's Push, Pull, Anxiety, Habit forces of progress to understand switch decisions.
category: growth
version: "1.0.0"
requires: []
optional_companions: []
---

## When this fires

Use when a team is trying to understand why users chose the product,
why users who considered it did not, or what a positioning statement
should emphasize. Fires when customer interviews produce vague "I liked
it" or "it was easier" answers instead of concrete switching narratives.
The skill structures the interview and the analysis around four forces
that must balance for a switch to happen, and turns qualitative research
into a prioritized list of product and messaging actions.

## Preconditions

- Access exists to users who switched to the product (or users who
  switched away) within the last six months — memory decays fast, and
  the clearest signal comes from recent switches.
- Interviewers can hold a conversation that goes timeline-first, not
  opinion-first. "What happened?" beats "what do you think?"
- The team is willing to hear that the product's positioning or
  messaging is wrong and to change it.

## Execution Workflow

1. Use Read on existing interview transcripts or customer success notes
   to sketch candidate switching stories. Pick seven to ten users who
   switched recently and can reconstruct the week leading up to it.
2. For each interview, run the timeline backward from purchase. What
   happened on the day of purchase? Seven days before? Thirty days
   before? Ninety days before? The first moment the user thought "I
   need something different" is usually where Push begins.
3. Map each story onto the four forces. Push is the dissatisfaction
   with the current solution — the specific pain, not a vague sense of
   "meh." Pull is the attraction of the new solution — what made it
   feel like the answer, specifically. Anxiety is the fear about
   switching — data loss, learning curve, internal politics, sunk
   investment. Habit is the inertia of the existing workflow — muscle
   memory, cached workflows, "good enough."
4. Tally the forces across stories. A Push that repeats across users is
   a real market signal. An Anxiety that repeats is a specific
   objection the product or positioning can defuse. A Habit that
   repeats tells the team what the switching cost actually is, in
   concrete units.
5. Translate the tally into product and messaging actions. Push gets
   amplified in positioning — acknowledge the pain directly. Pull
   gets amplified in the hero message and first-session experience.
   Anxiety gets reduced with migration tools, trials, and proof. Habit
   gets reduced with import, familiar patterns, and keyboard-shortcut
   parity.
6. Sanity-check balance. For a switch to happen, Push plus Pull must
   overcome Anxiety plus Habit. If Anxiety is the largest force in the
   tally, no amount of Pull amplification will move conversion; reduce
   Anxiety first.
7. Use TodoWrite to split actions between product (reduce Anxiety and
   Habit) and marketing (amplify Push and Pull). The two functions
   often work in parallel on the same research output.
8. Loop back in thirty to sixty days. As the product and messaging
   move, the force balance shifts; re-interview to confirm the new
   bottleneck is not the same as the old one.

## Rules: Do

- Interview users who recently switched, either to or from the product,
  and reconstruct a timeline.
- Map every story to all four forces — missing forces usually mean the
  interview was not pushed hard enough, not that the force is absent.
- Amplify Push and Pull in messaging; reduce Anxiety and Habit in
  product. The two halves of the framework map to two halves of the
  team.
- Treat the largest resistive force (Anxiety or Habit, whichever is
  bigger) as the immediate priority. Pull amplification alone cannot
  overcome heavy Anxiety.
- Revisit the force map after each round of changes; the new bottleneck
  is rarely the same as the old one.

## Rules: Don't

- Don't ask "what do you like about the product?" — it produces
  platitudes. Ask what happened on the day of purchase.
- Don't conflate Push (dissatisfaction) with Pull (attraction); they
  are independent forces and need distinct interventions.
- Don't treat Anxiety as irrational. A fear of losing five years of
  notes is a specific, legitimate cost — the product reduces it by
  flawless import, not by reassurance.
- Don't push Pull messaging without acknowledging Anxiety; users read
  the pitch as "this company doesn't understand what I'm worried
  about."
- Don't interview people who did not switch; they tell you nothing
  about the switching moment. Interview switchers in either direction.

## Expected Behavior

After applying the skill, the team stops arguing about whether the
product's messaging is "too emotional" or "too rational" and starts
asking which force is currently heaviest. Marketing ships messaging
changes tied to specific Push and Pull quotes from interviews. Product
ships Anxiety-reducers (import, trial, data export) and Habit-reducers
(keyboard shortcut parity, familiar layouts) in parallel, with both
teams knowing why the other is doing what they are doing.

Interviews themselves get sharper. The interviewer stops fishing for
feature requests and starts reconstructing decisions, which is the
research output that actually moves positioning. Over time the tally
of forces becomes a living artifact — updated after each cycle, used in
roadmap reviews, cited in messaging briefs.

## Quality Gates

- At least seven switching stories have been collected, each with a
  reconstructed timeline.
- Every story is mapped to all four forces, with specific quotes or
  incidents, not generic adjectives.
- The largest resistive force is named and the immediate action plan
  targets it.
- Product and marketing each own a concrete list of changes derived
  from the force map.
- A re-interview cadence is scheduled; the map is not a one-time
  deliverable.

## Companion Integration

Invoked by Matilha core skills (`matilha-scout`, `matilha-plan`) when
user research or positioning decisions surface. Pairs with
`growth-activation-aha-moment` (Anxiety reduction in onboarding is
often the fastest path to activation lift) and with the upstream
matilha-scout skill for research framing. Does not delegate to other
packs in v0.1.0.

## Output Artifacts

- Chat output only.

## Example Constraint Language

- Use "must" for: timeline-reconstruction interview structure,
  all-four-forces mapping per story.
- Use "should" for: seven-to-ten interviews per round, re-interview
  cadence after major changes.
- Use "may" for: the specific migration or import tools used to reduce
  Anxiety, which are product-dependent.

## Troubleshooting

- **"Users can't remember why they switched"**: The switch is too old.
  Recruit switchers from the last sixty days; memory on this decays
  quickly.
- **"Every story has weak Push"**: Either the product is serving a
  greenfield need (users not switching from anything), in which case
  the framework applies differently, or the interview is not probing
  hard enough for the specific pain. Try "walk me through the worst
  day you had with the old tool."
- **"Pull is strong but conversion is low"**: Look at Anxiety. Heavy
  Anxiety blocks a strong Pull; the product has a trust or migration
  problem, not a story problem.
- **"We reduced Anxiety but conversion did not move"**: The original
  Anxiety may not have been the real one. Re-interview and confirm;
  Anxiety tends to be specific, and generic "risk reduction" work
  often misses the exact fear.

## Concrete Example

A note-taking app interviews ten users who switched from Evernote in
the last quarter. Across the stories, Push shows up as Evernote's
price hike and performance decay. Pull shows up as clean markdown
syntax, offline-first behavior, and a fast editor. Anxiety is
overwhelming in every story: five-plus years of accumulated notes and
the fear that migration will lose something. Habit shows up as muscle
memory for Evernote's keyboard shortcuts. The roadmap splits cleanly.
Product ships an import tool that round-trips a real Evernote archive
losslessly, publishes a migration guide with screenshots, and maps
Evernote's top twenty shortcuts to the new app on day one. Marketing
leads the hero section with "Move five years of notes in ten minutes,"
which directly addresses the dominant Anxiety while still carrying
Pull. Conversion from trial to paid rises within sixty days without
any change to the product's core feature set.

## Sources

- `[[concepts/jtbd-positioning]]`
- `[[concepts/plg-estrategias-growth]]`
- `[[sources/product-htrategy]]`
- Inspired by Bob Moesta's Forces of Progress model and the broader
  Jobs-to-be-Done literature (Christensen, Ulwick), paraphrased
  further through Danilo's wiki synthesis of timeline-first interview
  structure and four-forces balance.
