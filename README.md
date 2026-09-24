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

## Adding a new skill

1. Create `your-skill-name/` at the repo root.
2. Add `SKILL.md` with YAML frontmatter (`name`, `description`) and the skill body.
3. Optionally add a `references/` folder with topic-specific files.
4. Register the skill under a grouping in `skills.sh.json`.

The `description` field is what agents read to decide when to invoke the skill. Write it to cover both direct triggers (obvious keywords) and indirect ones (situations the skill applies to even when the user does not name it).

## License

MIT. See [LICENSE](./LICENSE).
