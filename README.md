# working-with-obvious

An [Agent Skill](https://agentskills.io) for delegating work to the
[Obvious](https://obvious.ai) app through work orders — and driving every
order to a verified, merged delivery instead of a hopeful "Completed."

Built from real use: a real project run through Obvious in a single
intensive day — seven work orders with Obvious as the build workforce
(repo reorganizations, spec builds, document drafting, plan updates), with the agent commissioning, gating, verifying, and merging —
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
- **Verification at the destination.** Obvious builds real checks in —
  AutoBuild attaches QA evidence and gates merges — and still, in the
  general workspace a run marked complete delivered partially, and
  another stalled outright. The merge, the file, and the checked
  acceptance tests are the fact, on every surface.
- **Bounded cost, on purpose.** The ledger, per-member limits, and
  daily caps are built into Obvious; the pairing adds the discipline of
  reading the ledger before a batch, treating a promo pool's expiry as
  the planning deadline, and pinning premium models only where quality
  is the deliverable.
- **A paper trail that outlives the session.** Running logs, saved
  specs, and verified merges mean the next session — or the next agent —
  starts from the record, not from memory.

### When the pairing pays — and when it doesn't

If your work lives entirely inside one Obvious workspace and you're
glad to work its Inbox, Obvious's own loop — Blueprint, gates, QA
evidence, merge — is complete, and this pairing adds convenience, not
capability. The pairing pays when the work doesn't stay inside one
workspace:

- **The context lives elsewhere.** The user's rulings, other projects,
  other tools, and the rest of their life sit outside Obvious's memory.
  Muse holds them, and every order inherits them.
- **The checker must be independent.** Obvious grades its runs against
  the criteria it was given; Muse reads the actual deliverable with no
  stake in the run's self-report — and when a run dies, Muse is a
  second workforce that can ship the deliverable itself.
- **The user shouldn't operate anything.** Obvious has a mobile app;
  so does Muse. Reach was never the question. With the app alone you
  work the Inbox from your phone. With the pairing, decisions arrive
  where you already talk, batched across every project — and your
  whole job is to decide.

The skill is the contract between the two tools. Install it, and any
agent session that drives Obvious inherits the discipline: no
babysitting the user, no trusting a status screen, no merging what
hasn't been checked.

| | **Muse alone** | **Obvious alone** | **Muse + Obvious** |
|---|---|---|---|
| Executes the work | Yes — one thread, sequentially | Yes — focused work orders | Yes — Obvious executes, in parallel |
| Parallel orders | No — one thing at a time | Yes | Yes — and Muse sequences them |
| Knows the user and the project's history | Yes — memory, files, prior decisions | Yes — persistent memory inside its workspace | Yes — Muse's wider context, carried into each order |
| Writes the spec | Yes | Yes — AutoBuild drafts a Blueprint spec and waits for approval | Yes — Muse writes the order to a fixed anatomy (acceptance tests, stop rules) and fidelity-checks the run's plan against it |
| Verifies the delivery | At the destination, always | QA with evidence and review gates in AutoBuild; a general run can still read "complete" with delivery partial | Destination-checked on every surface; merged only when it passes |
| Handles the human's decisions | Asks in chat | Inbox queues decisions with context | Batched in the user's own chat, across every project at once |
| Watches cost | N/A | Ledger, per-member limits, and daily caps are built in | Ledger read before each batch; model pinning and Max mode deliberate |
| Paper trail | Logs and saved specs | Runs and decisions in the app; deliverables land where directed | Running log + verified merges, readable by the next session |
| The human's job | Direct the work | Work the Inbox | Decide — nothing else |

**Checked, not just claimed.** This comparison was audited on
2026-11-13 against Obvious's own published documentation — the
[Fusion](https://obvious.ai/fusion) and
[AutoBuild](https://obvious.ai/autobuild) pages and the official
product information at [obvious.ai/llm-info](https://obvious.ai/llm-info).
Obvious ships real review machinery of its own: persistent memory,
Blueprint specs with approval before building, QA evidence, review
gates, and an Inbox that queues decisions with context. Where an
earlier draft of this README understated any of that, it was
corrected. The pairing's claim is narrower and stronger: Muse sits
on those controls on the user's behalf, across every project and
tool the user runs — so the user never has to be the operator.

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
