---
name: matilha-growth-trigger
description: "Use when the user mentions AARRR, acquisition, activation, retention, referral, revenue, funnel, conversion, churn, North Star metric, viral coefficient, k-factor, JTBD, jobs-to-be-done, hook model, engagement, DAU, MAU, growth hacking, product-led growth, or any topic related to product growth and user metrics. Fires independently of compose to ensure matilha-growth-pack skills activate whenever growth domain appears."
category: growth-pack
version: "1.0.0"
---

## When this fires

User prompt mentions any keyword from matilha-growth-pack's domain: AARRR, acquisition, activation, retention, referral, revenue, funnel, conversion, churn, North Star metric, viral coefficient, k-factor, JTBD, jobs-to-be-done, hook model, engagement, DAU, MAU, growth hacking, product-led growth.

This skill fires independently of `matilha:matilha-compose` and `CLAUDE.md` activation rules — its keyword-rich description is the activation surface for the Skill tool's matcher. It guarantees that whenever the user prompt touches the growth domain, at least one matilha-growth-pack skill enters the conversation.

## Execution Workflow

1. **Pack presence check.** Inspect the ambient skill list for skills in the `matilha-growth-pack:*` namespace. Examples: `matilha-growth-pack:growth-aarrr-funnel`, `matilha-growth-pack:growth-north-star-metric`, `matilha-growth-pack:growth-jtbd-forces`.

2. **Pack installed path.** If ≥1 skill from `matilha-growth-pack` is visible:
   - Identify the user's sub-intent within the growth domain (picking a North Star, diagnosing churn, designing a referral loop, mapping AARRR, defining ICP, modeling pricing, etc.).
   - Emit a compact domain acknowledgment (≤2 lines — no full sigil, that belongs to compose). Example: `Growth domain detected. Pulling matilha-growth-pack guidance for <sub-intent>.`
   - Invoke the most relevant pack skill via the Skill tool. Prefer one specific skill over listing many.

3. **Pack not installed path.** If no `matilha-growth-pack` skills are visible:
   - Emit: "Growth skills not installed. Run `/matilha-install` and select `growth` to add 20 growth skills."
   - Proceed with default flow (`matilha:matilha-compose` if visible, otherwise `superpowers:brainstorming`).

## Rules

- Do NOT emit the full compose sigil. The sigil belongs to compose; this skill emits a compact pack-specific acknowledgment.
- Do NOT block on pack absence — emit the nudge and continue with the default flow.
- Prefer invoking a specific pack skill over listing all skills.
- This trigger is a routing surface, not a craft skill — hand off to the chosen pack skill quickly.

## Why this exists

Wave 5h adds deterministic activation surfaces to compensate for probabilistic Skill-tool matching. Compose's routing table covers the central path; this trigger covers prompts that bypass compose (e.g., when CLAUDE.md is absent, or when a domain keyword appears mid-conversation without a compose-classifiable phase). Together they form the Maximum Activation guarantee for matilha-growth-pack.
