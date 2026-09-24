# agent-skills

Modular skills for AI coding agents that support the skills.sh format (Claude Code, Codex, and others).

Each skill lives in its own directory and installs individually.

## Skills

### [pilot-first-outreach](./pilot-first-outreach)

For anyone job hunting, weighing a career move, or looking for consulting, fractional, or cofounder work — without CVs, applications, or generic pitches.

Runs four parallel workstreams:

- **Wedge** — narrow the user's claim to something provable
- **Map** — identify specific companies where that claim maps to visible missing revenue
- **Signal** — build public artifacts that pull the right people in
- **Trial** — structure a scoped, reversible pilot the target has little reason to refuse

Produces: positioning brief, scored target list, weekly artifact plan, one-page call plan, one-page pilot proposal.

## Install

Send this to Claude Code, Codex, or another agent with terminal access:

> Run `npx skills add sadiqkhzn/agent-skills --skill pilot-first-outreach` and set it up for this agent.

Or from a terminal:

```bash
npx skills add sadiqkhzn/agent-skills --skill pilot-first-outreach
```

Add `-g` to install globally across projects.

## Once installed

> Use pilot-first-outreach to help me find companies where my experience is valuable. Start with the wedge, then build the target list and outreach.

If further along:

> Call is booked with a founder tomorrow — build the call plan.
> They asked me to propose a trial — design the pilot.

## Skill families

Skills in this repo are organized into **families**. A family is a set of skills that share a domain and hand off to each other during a session. A job-hunt skill and a Tesla resale skill do not belong in the same family; a job-hunt skill and a resume-rewrite skill do.

Families are the groupings in `skills.sh.json`. Each grouping's title is the family name; the skills listed under it are members.

Within a family:

- Each SKILL.md includes a **Related skills** section naming siblings and the specific conditions that trigger a hand-off.
- Hand-offs are declared in both directions so either skill can initiate.
- The agent loads sibling skills on demand mid-session — the user does not install them separately or restart.
- A workflow can loop across siblings for as many passes as the task needs (for example: outreach skill triggers case-study skill, which returns control, which triggers outreach again for the next target).

Across families:

- No cross-references between SKILL.md files.
- No shared `references/` directory.
- Each family stays self-contained so unrelated domains do not accidentally invoke each other.

Current families:

- **Career and work** — [pilot-first-outreach](./pilot-first-outreach) (single member for now; siblings will chain when added)

## Adding a new skill

1. Decide whether the skill belongs in an existing family. Belongs when it operates in the same domain and can plausibly hand off to or from an existing member. Otherwise, start a new family.
2. Create `your-skill-name/` at the repo root.
3. Add `SKILL.md` with YAML frontmatter (`name`, `description`) and the skill body.
4. Optionally add a `references/` folder with topic-specific files.
5. Register the skill in `skills.sh.json`:
   - Existing family — append the skill name to that grouping's `skills` array.
   - New family — add a new grouping with its title, description, and the skill as its first member.
6. If joining an existing family, add a **Related skills** section to the new SKILL.md and update siblings' Related skills sections to point back. State the specific conditions that trigger each hand-off.

The `description` field is what agents read to decide when to invoke the skill. Write it to cover both direct triggers (obvious keywords) and indirect ones (situations the skill applies to even when the user does not name it). Hand-off triggers should be phrased so the agent recognizes them from user context, not from the previous skill's output.

## License

MIT. See [LICENSE](./LICENSE).
