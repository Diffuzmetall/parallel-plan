# Work discovery and bounded idle rechecks

This is a design contract for the runtime or operator, not an installed watcher. Use the existing native scheduler and task board when implementing an authorized change; do not add an external model polling loop by default.

## Primary mechanism: work events

A free actor watches eligible work availability, not the completion of an arbitrary large task. A newly ready output or direct handoff should produce a compact hint in the same native conversation. The hint is neither assignment nor completion: the actor reads current state and claims atomically. Another actor may have won the task first.

An actor retaining a necessary unfinished claim can wait for exact dependencies. That wait keeps its ALL-DONE meaning. Broader work discovery must not pretend those dependencies passed. To switch work, checkpoint and safely relinquish the current claim and resources through the existing protocol.

Map these semantics to the actual host, if it supports them; see [Integrations](Integrations.md) for an optional DeLM mapping. Inspect saved wait and delivery state before cancellation or replacement. An accepted or committed wake cannot simply be retracted. Unsupported scheduling remains an explicit capability gap, not a reason to install another loop.

## Idle safety net

If an idle safety net is requested, name an agreed threshold, wake budget and stopping condition. Ten minutes is an illustrative threshold, not a universal default or authorization for model calls. Measure from verified idle waiting, not the last visible message. Busy tools, builds, human-paused actors and unknown execution state must not be treated as idle.

A deterministic native check can read actor execution, claims, saved waits, board revision and ready work without calling a model. It should:

- wake an eligible idle actor when useful new ready work or a handoff exists, using deduplicated native delivery;
- request one bounded decomposition review when a broad remaining gate may hide independent work and no such review has occurred for this wait/board state;
- keep waiting without model spend when the review found no useful work and nothing relevant changed;
- preserve explicit human/external blockers and all approval boundaries.

For a broad-gate review, nudge one eligible participant, not every sleeper. The actor proposes or creates authorized missing outputs while respecting ownership of the existing parent; it does not rewrite another owner's claimed task. New ready outputs can then wake other peers. Parent/child edges must remain acyclic.

Deduplicate by exact conversation, wait generation and relevant board state. Do not re-wake on observer refreshes or unrelated status chatter. Reconcile uncertain admission instead of blind resend. A read-only observer is not the owner of scheduling or conversations and must not become one.

## Acceptance for an implementation

- Ready work wakes a free waiter without a periodic model poll.
- A free actor stuck in an obsolete named wait gets a bounded reevaluation; dependency readiness remains false until the named outputs are actually DONE.
- A claimed blocked actor is not reassigned while its writes or leases remain active.
- A busy actor with a historical waiting record is not interrupted.
- A lost notification/restart does not create duplicate accepted inputs or another session owner.
- Ten minutes with unchanged, genuinely unavailable work does not trigger endless model calls.
- Human stops, denied permissions and missing runtime capabilities remain blockers, never automatic resume permission.

Report separately: documented policy, tested runtime implementation, installed version and activation in the exact live sessions.
