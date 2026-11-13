# Gotchas — Working With Obvious

Failure modes observed in real use (November 2026, pre-release builds).
Check here before diagnosing a stuck or strange run.

## "Completed" does not mean delivered
A run's chat can end with a success message while nothing reached the
destination. Delivery happens in the run's Deliver step and lands as a
GitHub PR (or the named artifact). **Rule:** verify at the destination —
repo, file, page — every time. Conversely, a first empty read of the PR
list has been wrong; re-check before reporting "nothing delivered."

## The out-of-credits banner can lie
An in-app "out of credits" banner once appeared while the workspace's
promo pool was nearly full (997+ of 1,000 credits remaining). The banner
apparently tracked a different bucket than the promo grant. **Rule:** open
the credits ledger, identify the grant, its remaining balance, and its
expiry, and reason from those numbers — never from the banner.

## Promo credits expire
Hackathon and promo grants carry an expiry date (the observed pool expired
~12 months after grant). Work planned "for later" against a promo pool is
planned against money that may not exist. **Rule:** treat promo credit as
spend-it-on-real-work-today, and never put a card on file by accident to
"keep it running" without the user's explicit decision.

## The cross-task Approve button
An "Approve" control visible in the Inbox belonged to a *different* work
order's pull request than the one under review. Clicking it would have
approved the wrong delivery. **Rule:** before pressing any approval,
confirm the PR number, title, and owning task on the control itself.
Approvals are per-artifact, never per-screen.

## A run can have no approval control at all
One order's run reached a step requiring approval, and no approve control
existed on any surface — app, inbox, or run view (a UI defect). The run
could neither proceed nor be dismissed. **Rule:** if a run is stuck on a
gate that doesn't exist, stop waiting on it. Produce the deliverable by
another route, record the run as superseded in the project log, and
dismiss its ask if it ever surfaces.

## Model selection can be policy-blocked
Pinning models (per chat, per agent, per routine) can be disabled at the
workspace level: `models.list`, `tasks.create --model`, and
`agents.create --modelSelection` all return FORBIDDEN for the user.
This is not a login problem and cannot be fixed inside a run. Only the
workspace owner can enable it (web app → workspace settings → Models).
**Rule:** report the exact setting and screen; do not flip workspace-wide
settings on the user's behalf, because pinned non-included models bill
separately at usage rates — a spend decision, not a convenience toggle.

## Obvious agents have no email — and never will mid-task
The agent inside Obvious has no inbox of its own. It can act in the user's
connected mail as the user, but it cannot create an email account, receive
verification codes at an address of its own, or complete third-party
sign-ups (CAPTCHAs are handed to humans by design, there is no phone
number, and registering as a person misrepresents it). **Rule:** never
design a workflow that requires an agent-owned account on an external
site — panel seats, logins, and verifications route through the user or
through agent-native mailbox services the user owns.

## Custom agents inside a run need approval — inside that run
A run that creates a helper agent (a judge, a reviewer) pauses for the
creation to be approved in-run. That approval is routine and inside the
agent's mandate; press it. But read what is being created first: name,
memory setting, and tools. For judges and reviewers, memory disabled is
usually the right default so verdicts stay independent.

## The Inbox contains other projects' asks
A workspace Inbox mixes every project's requests. Items that are not this
project's — however urgent they look — are not this task's business.
**Rule:** act only on asks belonging to the order you are running.

## A spec gap becomes a delivery defect
Every fidelity failure traced so far was a sentence the spec didn't
contain: a file that should not change, a status that needed defining, a
figure that needed a source. **Rule:** when a delivery disappoints, fix
the spec first (clean copy, see SKILL.md), and only then re-run. Re-running
a vague spec produces a second vague delivery at full price.
