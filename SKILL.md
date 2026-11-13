---
name: working-with-obvious
description: Delegates build, document, and research work to the Obvious desktop app through work orders, then drives each order to a verified, merged delivery. Use when the user asks to send work to Obvious, start or revise a work order, check on an Obvious run, approve something a run is waiting on, or verify and merge what Obvious delivered. Not for work the agent should simply do itself in chat, and not for Obvious workspace settings such as model selection, which only the workspace owner can change.
license: MIT
metadata:
  version: "1.0.0"
---

# Working With Obvious

Obvious is a workforce, not a chat window. The agent commissions work the way a
good chief of staff does: a precise order, gates pressed without being chased,
deliveries verified against the order, and only genuine decisions brought back
to the user — batched, in chat, never as homework inside the app.

## The operating contract

- **No babysitting.** The agent writes the spec, submits the work order,
  approves in-run gates, answers routine run questions, fidelity-checks the
  delivery, and merges verified pull requests. The user is not sent into the
  app to press buttons the agent can press.
- **Decisions travel up, work travels down.** Rulings, scope changes, and
  money come back to the user in chat, batched into one list with the evidence
  and any lean labeled as a lean. Everything else is handled inside the run.
- **A delivery claim is not a delivery.** A run's "Completed" in chat means
  the conversation ended. Delivery is the artifact the order promised — in
  practice a GitHub pull request from the run's Deliver step, or the named
  file in the named place. Verify at the destination, never from the claim.
- **One order, one outcome.** Each work order carries a single deliverable.
  Bundled orders produce unverifiable deliveries.

## Write the order

A work order is a contract; the run will be graded against it. Include:

1. **Outcome** — the deliverable, named exactly (files, paths, PR against
   which repo and branch).
2. **Source material** — the files or text the work builds on, by path. Never
   assume the run can see the chat, the user's memory, or other orders.
3. **Acceptance tests** — how the agent will verify the delivery: counts,
   headings, figures traced to sources, statuses, screenshots where visual.
4. **Stop rules** — what the run must never do: connect accounts, accept API
   keys, post publicly, spend money, exceed the named scope.
5. **Echo requirement** — the run restates the delivery in the project's
   running log or record file, so the paper trail exists outside the app.

Use the skeleton in `assets/work-order-template.md`.

## Run the order

- Submit, then press every in-run gate yourself: agent creations, spec
  confirmations, routine clarifying questions with an obvious answer inside
  the order's scope.
- If the run asks a question that is actually a user decision (scope, money,
  a ruling), do not answer it from the run. Park it, finish what can finish,
  and bring it back in the next batch.
- Expect the order to deliver as a PR. Check the destination repo when the
  run reports completion — and re-check once if the first read shows nothing;
  an empty list read has been wrong before.

## Revise an order

- Use the run's formal "Ask for changes" route, not a new chat message.
- Send **one complete clean copy** of the revised spec — every point, in
  full, replacing the original. Patch lists and deltas drift; a clean copy
  is the new contract.
- Re-verify the revised spec the run returns against the clean copy before
  approving it: faithfulness is checked line by line, not skimmed.

## Verify and merge

1. Fidelity-check the PR against the order: files, figures, statuses, and
   anything the order said must *not* change.
2. Run the order's acceptance tests at the destination (repo state, live
   page, file contents) — not from the run's summary.
3. Merge only what passes. Record the merge (commit, PR number) in the
   project's running log in the same step.
4. If a delivery fails, notify the owning run with the item, the acceptance
   test, what was observed, and what fixed looks like.

## Credits and plan discipline

- Read the credits ledger before concluding anything about balance: in-app
  "out of credits" banners have misreported a nearly full promo pool.
- Promo credits expire. Know the expiry date and treat the pool as a
  bounded resource: worth spending on real orders today, never a reason to
  invent work.
- Know what is *not* covered: models pinned outside the plan's included
  routing bill separately at usage rates.

## Boundaries

- Never put passwords, API keys, or private data the task does not need
  into a spec, a run, or project memory.
- The agent does not change workspace-wide settings (for example enabling
  model selection). When a run is blocked by such a setting, name the exact
  setting and screen for the user and let them decide.
- When a run cannot proceed (a UI defect, a policy block), say what is
  blocked, produce the deliverable by another route if the user still wants
  it, and mark the run superseded rather than leaving it "in progress."

## When something goes wrong

Read `references/gotchas.md` before improvising: it records the failure
modes already paid for — false credit alarms, cross-task approval buttons,
missing approval controls, policy-blocked model selection, and why no
workflow may depend on an agent-owned email account.
