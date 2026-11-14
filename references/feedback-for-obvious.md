# Feedback for Obvious — what would make the middleman unnecessary

*From a Frontier Build participant who ran a real project through
Obvious in a single day — seven work orders, all delivered as PRs —
with an external agent (Muse) acting as operator: writing the specs,
pressing the gates, verifying deliveries, and batching every decision
for the human. Everything below is a place where that agent was
filling a gap in the product. Close these, and the pairing this
feedback is attached to becomes unnecessary — which is the outcome
I'd most like to buy from you.*

## The five that matter most

1. **An operator seat.** Today a human has to work the Inbox: press
   gates, answer routine run questions, notice stalls. Give the
   workspace an operator — a built-in chief-of-staff agent, or an open
   API/MCP surface that lets an external agent do it — that clears
   routine gates from the spec and project memory, and escalates only
   genuine decisions. Until that seat exists inside Obvious, users
   will bolt an agent onto the outside of it.

2. **Batched, portable decisions.** The Inbox queues decisions per
   project, inside the app. Decisions should consolidate across every
   project into one digest, delivered where the user already talks
   (chat, email, Slack), answerable in place, each one carrying its
   evidence and a recommended answer with its reasoning labeled. One
   sitting, all projects, then silence.

3. **A verifier that doesn't grade its own homework.** AutoBuild's QA
   evidence is genuinely good — and in the general workspace I still
   watched a run marked complete deliver partially, and another stall
   with no delivery and no alarm. Add an independent verification pass
   that re-checks the destination itself (repo state, file contents,
   acceptance tests) and shows a claimed-vs-delivered diff. And make
   stalled or blocked runs raise their hand: a dead run should never
   be silent.

4. **Portable, inspectable memory.** Persistent memory inside a
   workspace is a strong start. What makes an external agent necessary
   is everything the workspace can't hold: the user's rulings, other
   projects, other tools. Let memory span workspaces, be viewable and
   correctable by the user ("show me what you know about X"), and be
   exportable/importable so a user's context isn't trapped in one
   vendor's walls — including permissioned sharing with the user's
   other agents.

5. **Approval integrity.** Every approval control should be bound —
   visibly and in the URL — to the exact task and artifact it approves.
   I was shown an Approve button that belonged to a different task's
   PR in the wrong context; on a tired day that's a wrong merge. And
   when a run's next step needs a control, the control must exist:
   one of my runs stalled outright because the approval surface it
   waited on wasn't there.

## Smaller, but real

- **Policy transparency at the point of need.** Model selection was
  disabled for my user by workspace policy; I learned this from
  FORBIDDEN errors, by trial. Say it in the product, to the user and
  to agents, with the exact admin path — and let owners delegate
  bounded permissions (one project's models) without workspace-wide
  flips.
- **Cost truth, pushed.** My credits ledger was healthy while an
  in-app banner said I was out of credits. Reconcile the two, put
  per-run cost attribution in the run record (model, credits), and
  push burn/expiry alerts outside the app before a pool dies.
- **A designed human-handoff for identity walls.** Your agents
  (correctly) won't create accounts, take verification codes, or
  solve CAPTCHAs. Build the graceful version: a first-party agent
  mailbox/identity for agent-legitimate mail, and a one-tap "this
  step needs a human" handoff instead of a dead end.

## The short version

Obvious already executes, remembers, specs, and checks. What it
doesn't yet do is *operate itself on the user's behalf across
everything the user runs* — and operate honestly about its own
state. The day it does, the external operator retires, and I'll
cheerfully archive the skill that describes him.
