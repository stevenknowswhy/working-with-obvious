# working-with-obvious

An [Agent Skill](https://agentskills.io) for delegating work to the
[Obvious](https://obvious.ai) app through work orders — and driving every
order to a verified, merged delivery instead of a hopeful "Completed."

Built from real use: a multi-week project run with Obvious as the build
workforce (repo reorganizations, spec builds, document drafting, plan
updates), with the agent commissioning, gating, verifying, and merging —
and the human deciding, in batches, only what is genuinely theirs to decide.

## Why Muse + Obvious

Neither tool does the other's job. Obvious executes — it runs focused
work orders inside its own app, in parallel, against real deliverables.
Muse owns everything around the execution: the user's context and
memory, the decisions, the spec, and the proof that what came back is
what was asked for. Paired, you get:

- **Parallel hands, one accountable head.** Several orders run at once,
  each landing as its own pull request or named file. Muse sequences
  them, watches for the ones that stall, and keeps the user out of the
  tool's inbox entirely.
- **Decisions stay with the human, in batches.** The runs execute; the
  choices that are genuinely the user's — scope, money, rulings — come
  back as one numbered list with evidence and labeled recommendations,
  not as a drip of app notifications.
- **Specs instead of vibes.** Every order is written to the same anatomy
  — outcome, named sources, acceptance tests, stop rules, an echo into
  the project record — so the work is checkable on arrival instead of
  arguable.
- **Verification at the destination.** "Completed" in the app is a
  claim; the merge, the file, and the checked acceptance tests are the
  fact. Muse reads the destination, not the status screen.
- **Bounded cost, on purpose.** The pairing treats credits as a dated,
  finite pool: read the ledger first, leave routine work on the included
  model routing, and pin premium models only where quality is the
  deliverable.
- **A paper trail that outlives the session.** Running logs, saved
  specs, and verified merges mean the next session — or the next agent —
  starts from the record, not from memory.

The skill is the contract between the two tools. Install it, and any
agent session that drives Obvious inherits the discipline: no
babysitting the user, no trusting a status screen, no merging what
hasn't been checked.

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
- **The field notes** (`references/field-notes.md`) — the optimization
  playbook: spend the promo pool backwards from its expiry, pin models
  only where quality is the deliverable, fidelity-check the spec a run
  returns before approving it, keep protocols (not state) in project
  memory, and separate the builder from the verifier.

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
references/field-notes.md       # insights + optimization playbook
assets/work-order-template.md   # the spec skeleton every order starts from
```

## License

MIT — see `LICENSE`. Use it, fork it, improve it; if your Obvious build
teaches you a new gotcha, a pull request adding it to the list is the
best thank-you.
