# Field Notes — Insights and Optimizations for Working With Obvious

What real use taught, beyond the failure modes in `gotchas.md`. These are
the practices that made the difference between Obvious as a novelty and
Obvious as a workforce.

## Spend the pool like it expires — because it does

- **Promo pools are bounded and dated.** All seven work orders of the
  observed project ran in a single day, and the workspace ledger showed
  ~2 credits of total burn over the preceding week against a 1,000-credit
  promo grant: the constraint was never the balance, it was the expiry.
  Plan backwards from the expiry date; batch the day's orders instead of
  dribbling them out, and front-load the highest-value builds.
- **Read the ledger before a batch, not after.** Grants, burn, and expiry
  are all in the credits view. A five-second ledger check before a big
  batch beats discovering the economics mid-run.
- **Pin models deliberately, or not at all.** Obvious can pin a model per
  chat, per agent, and per routine (Anthropic, OpenAI, Z.ai, and others) —
  but pinned non-included models bill separately at usage rates, outside
  plan and promo credit. The optimization: leave routine work on the
  included routing, and pin a strong model only where output quality *is*
  the deliverable — a judge, a reviewer, a final spec. Pinning everything
  is how a free day turns into an invoice.
- **Design around policy walls instead of fighting them.** When model
  selection is disabled for the workspace, orders that *need* a pinned
  model are orders designed wrong. Spec quality beats model shopping:
  a precise order on the default routing outperformed a vague order that
  was waiting for a better model.

## Spec quality is the whole cost curve

- **A vague spec doesn't produce a cheap draft; it produces a full-price
  wrong delivery and a full-price re-run.** Every fidelity failure traced
  in real use was a missing sentence in the spec — a file that should not
  change, a term that needed defining, a figure that needed a source.
  Writing the acceptance tests *is* the work; the run is the cheap part.
- **Fidelity-check the spec the run returns before approving it.** Runs
  that restate their understanding (a revised spec, a plan) offer the
  cheapest correction point in the whole pipeline — line-by-line against
  the clean copy you sent. Approving a drifted spec builds the wrong
  thing at full fidelity.
- **One complete clean copy beats five patch messages.** Revisions sent
  as deltas drift: the run merges them unevenly and the contract blurs.
  A single replacement spec keeps one version of the truth — and gives
  the fidelity check something exact to check against.
- **Stop rules are a feature, not a lack of trust.** "No account
  connections, no API keys, no posting, nothing outside the named scope"
  prevented an entire class of runaway behavior — and made runs *faster*,
  because the agent stopped exploring doors it didn't need.

## Structure the work so verification stays cheap

- **One order, one deliverable, one PR.** Seven orders ran in parallel on
  one project (reorganization, three document jobs, a build, a copy pass)
  and every one was verifiable in minutes because each landed as its own
  pull request against the real repo. Bundled orders would have made the
  same work unverifiable as a set.
- **Make the PR — or the named file in the named place — the only
  definition of done.** In-app artifacts are drafts. The moment "done"
  means "merged at the destination," most reporting arguments disappear.
- **Require the echo.** Every order ends by writing its delivery into the
  project's running log. Without that, delivered work is invisible to the
  next session, the next agent, and the human — and gets commissioned
  twice.
- **Separate the builder from the verifier.** The deliveries that looked
  finished and weren't (a setup job whose status file never landed) were
  caught by an independent verification pass checking evidence at the
  destination on a schedule — not by asking the builder again. If the
  work matters, someone who didn't do it checks it.

## Use the platform's memory on purpose

- **Project memory is for protocols, not state.** Saving the panel
  protocol (how a review round runs, what a valid reply looks like) to
  project memory meant every later run started from the same rules
  without re-briefing. Fast-changing state — balances, statuses, today's
  decisions — goes stale in memory and misleads; keep it in the project
  record instead.
- **Build repeated roles once, as custom agents.** A judge agent created
  for one review round served every later round. Create the role when
  the second use appears, approve its creation in-run, and set its memory
  deliberately: for judges and reviewers, memory *disabled* keeps each
  verdict independent.
- **Keep one project per deliverable-domain.** Runs deliver inside their
  own project; a shared project blurs destinations, and the workspace
  Inbox mixes every project's asks together. Triage by project first.

## Keep the human's job small and real

- **Batch decisions; never dribble them.** Twenty-one rulings accumulated
  across a day of runs were decided in one sitting because they arrived
  as one numbered list with evidence and labeled leans. A user pinged
  per-question stops answering — and the runs stall behind them.
- **Name the owner-only actions plainly.** Some steps are structurally
  the user's: creating a repository, granting an app access to it,
  flipping a workspace-wide setting. The agent's job is to arrive with
  the exact screen and the exact click, not a tour of the settings app.
- **Have an exit route for every order.** Once, a platform defect (a
  missing approval control) stranded a run entirely. The work still
  shipped — produced agent-side — because the outcome mattered more than
  the channel. Decide in advance: if this run dies, how does the
  deliverable still happen?

## The pattern underneath all of it

Obvious works best when it is treated as a *contractor with a contract*,
not a colleague with a vibe: a written scope, acceptance tests, a paper
trail, verified delivery, and a human who decides the few things that are
actually theirs. Every optimization above is that sentence applied to a
different surface — credits, specs, memory, or attention.

## Already built in — don't rebuild it

Audited 2026-11-13 against Obvious's own published documentation
(obvious.ai/fusion, obvious.ai/autobuild, obvious.ai/llm-info). The
platform ships more operating machinery than a new user expects; the
pairing's job is to *operate* it, not recreate it:

- **Persistent memory** — facts, decisions, and conversation history
  across sessions, inside the workspace. (What it doesn't hold: the
  user's context outside Obvious. That's the layer the driving agent
  carries in.)
- **Blueprint specs** — AutoBuild researches the codebase, drafts the
  spec with its tests, and waits for approval before building.
- **Loop Designer** — custom process steps, handoffs, and human
  approval gates.
- **QA with evidence** — checks run against your criteria with
  screenshots, test results, and API responses attached; failed checks
  are fixed and retested before you see them.
- **Review gates and merge rules** — required checks and a named final
  say on merges; completion gates backed by database evidence.
- **The Inbox** — decisions and blocked work queued with context,
  across projects.
- **Cost controls** — per-member credit limits, daily caps, an
  account-menu view of remaining allowance, and a warning before
  switching to a separately billed model.
- **Skills and knowledge** — the platform learns your codebase and
  docs and applies your team's existing skills.
- **Self-improvement** — runs propose fixes to their own instructions,
  which wait for your approval.

An earlier draft of the companion README understated several of these
(it described Obvious as starting from the order, reporting
"Completed," and letting credits burn invisibly). All three were
wrong against the vendor's own docs and were corrected — the
destination-verification rule survives not because Obvious lacks
checks, but because a checked claim is still a claim until someone
reads the deliverable.
