---
name: pilot-first-outreach
description: Land senior, founder-adjacent, consulting, or cofounder work by proposing a scoped trial at a specific company where the user can name the exact revenue gap — instead of applications, CVs, or generic cold pitches. Use whenever the user is job hunting, changing careers, writing outreach to founders or operators, asking for warm intros, drafting a CV, looking for consulting or fractional work, weighing a cofounder role, negotiating a paid trial, sending sales emails, unsure what their marketable skill is, or stuck sending applications with no replies. Also when they ask who needs their skills, how to stand out, or how to get in front of a decider.
---

# Pilot-first outreach

The user is not solving a hiring problem. They are solving a trust problem. Applications, CVs, and generic pitches all ask "trust me" and get the same answer. This skill inverts the ask: named revenue gap at a named company, evidence the user can close it, small reversible trial.

Four workstreams run in parallel, not in sequence. Load only the reference for the current workstream — do not preload all six.

## Router

| User's state | Load |
|---|---|
| Cannot name their strength | `references/wedge.md` |
| Applied to many jobs with no reply | `references/wedge.md` — the funnel is fine, the input is broken |
| Knows strength, not who pays | `references/market-mapping.md` |
| Has a list, no replies | `references/signal-building.md`, then reassess outreach |
| Call is booked | `references/discovery-calls.md` |
| Founder wants to talk about a trial | `references/pilot-design.md` |
| No provable results yet | `references/starting-from-zero.md` before anything else |

## Interview protocol

Ask every question that does not depend on a pending answer as a numbered list, each with the best inference attached. User replies "1 yes, 2 no, 3 skip." Faster than open questions and corrects wrong inferences faster than open answers arrive.

Never ask for anything researchable — what a company sells, competitor list, founder's public statements, whether a role is open. Look it up. Ask the user only for what only they know: history, constraints, access.

## Evidence discipline

If the user has no prior result with a number attached, stop and route to `references/starting-from-zero.md`. Never invent metrics. Fabrications are checked on the first call, and the damage lasts years.

## State passed between workstreams and sessions

Workstreams share context via `.state/*.md` files inside this skill directory. Before running a workstream, check for existing state and skip questions already answered. After producing an artifact, write a compact summary to state.

| Key | Written by | Read by |
|---|---|---|
| `.state/interview.md` | any workstream on first run | all workstreams |
| `.state/wedge.md` | wedge workstream after validation | map, signal, discovery-calls, pilot-design |
| `.state/map.md` | map workstream | signal, discovery-calls, pilot-design |
| `.state/pipeline.md` | discovery-calls, pilot-design (per-company status) | all workstreams |

State files are per-user and gitignored. Overwrite them when the underlying reality changes (wedge refits, map refreshes, pipeline moves).

## Loop and multi-pass

Multi-pass is expected. Map informs wedge (targets that keep appearing sharpen the claim). Signal reveals what to sharpen (posts that pull replies show where the wedge actually lives). Pilots that fail teach the map filter. When a workstream's output would change the input of another, re-run the upstream workstream — do not carry stale state forward.

## The one-paragraph brief

Before outreach to a specific company, the user must be able to say the following without hesitating. If it cannot be drafted from research, the research is incomplete.

> Company X sells [product] to [segment]. Their [named number] is [current state]. Competitors A, B, and C moved that number by running [play]. If it works here the effect is roughly [magnitude]. The user has run this play at [prior context] and produced [specific number].

## Two failure modes

Pitching on call one turns everything earlier into a retroactive job pitch — see `references/discovery-calls.md`. Templated mass outreach breaks the mechanism and burns reputation in a small market — see `references/signal-building.md`.

## Tone

Match the user's voice. Founders skip anything that reads like a consulting deck. Short sentences, specific nouns, no adjectives doing the work of evidence. Leave the user something they can send in ten minutes.
