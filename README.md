# working-with-obvious

An [Agent Skill](https://agentskills.io) for delegating work to the
[Obvious](https://obvious.ai) app through work orders — and driving every
order to a verified, merged delivery instead of a hopeful "Completed."

Built from real use: a multi-week project run with Obvious as the build
workforce (repo reorganizations, spec builds, document drafting, plan
updates), with the agent commissioning, gating, verifying, and merging —
and the human deciding, in batches, only what is genuinely theirs to decide.

## What it teaches an agent

- **The operating contract** — no babysitting: the agent writes specs,
  submits orders, presses in-run gates, verifies deliveries, and merges;
  decisions (rulings, scope, money) come back to the human batched, in
  chat, never as homework inside the app.
- **Work-order craft** — outcome, source material, acceptance tests, stop
  rules, and an echo requirement, so a delivery can be graded against its
  order. Template included in `assets/`.
- **Revision by clean copy** — one complete replacement spec through the
  run's formal change route, never a drifting list of patches.
- **Verification discipline** — a run's "Completed" is not a delivery;
  check the destination (the PR, the file, the page), fidelity-check
  against the order, merge only what passes.
- **Credits discipline** — read the ledger, not the banner; promo pools
  expire; pinned models can bill outside the plan.
- **The gotchas** (`references/gotchas.md`) — failure modes already paid
  for: a false out-of-credits alarm over a nearly full pool, an Approve
  button that belonged to a different task's PR, a run stuck on an
  approval control that didn't exist, workspace-policy-blocked model
  selection, and why no workflow may depend on an agent-owned email
  account.

## Install

This repository is a standard Agent Skills folder. Clone it into your
agent's skills directory under the name `working-with-obvious`:

```bash
# Claude Code (project)
git clone https://github.com/stevenknowswhy/working-with-obvious .claude/skills/working-with-obvious

# Any agent that reads the Agent Skills format
git clone https://github.com/stevenknowswhy/working-with-obvious <your-skills-dir>/working-with-obvious
```

The agent reads the name and description at startup and loads the rest
only when a request matches — the gotchas file loads only when a run goes
wrong, which is exactly when it's needed.

## Layout

```
SKILL.md                        # the method (loads when the skill triggers)
references/gotchas.md           # failure modes, loaded on trouble
assets/work-order-template.md   # the spec skeleton every order starts from
```

## License

MIT — see `LICENSE`. Use it, fork it, improve it; if your Obvious build
teaches you a new gotcha, a pull request adding it to the list is the
best thank-you.
