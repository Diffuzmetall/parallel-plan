# Designing useful slices

## The unit is behavior, not a layer

A vertical slice delivers one observable capability through the boundaries that capability requires. A supporting output unblocks a named slice. An experiment resolves one consequential unknown. A check supplies evidence for a claim. These are different outputs; do not label them all complete product features.

A slice is not a service, module, ticket, pull request or agent. One behavior may span several modules; one cohesive module may serve several slices. The plan describes delivery order without forcing the code to mirror the task graph.

The first result should matter to an intended user or operator and exercise the project's uncertain boundary. A health endpoint is not the first slice of a durable editor unless health reporting is itself the agreed capability. When all realistic slices need groundwork, bound that groundwork and name the first real probe it enables.

## Useful splitting choices

Select a split that preserves meaning and safety. The table offers alternatives, not a required sequence.

| Broad request | Useful cut | Trap to avoid |
| --- | --- | --- |
| Several user workflows | One complete workflow, then another | All screens before any working action |
| Many supported formats or channels | One real format/channel through the full path | Hardcoded sample output instead of a real implementation |
| Many business rules | One supported rule set with unsupported inputs explicitly rejected | Silently accepting cases whose rules are deferred |
| Large data volume | Correct bounded workload, then scale to an agreed load | Claiming production capacity from a tiny fixture |
| External integration | One real operation in an authorized sandbox, then broader cases | Calling mocked compatibility a passed integration |
| Risky state transition | One complete transition with its authority and integrity checks | Happy path now, protection from data loss later |
| Replacement or migration | One bounded cohort/path migrated and verified, then expansion | A whole new platform before any real consumer uses it |
| Uncertain interaction or semantics | One bounded experiment and recorded decision | A permanent prototype phase or prototype counted as production |

If a slice cannot be checked without several unfinished outputs, either reduce it to a meaningful supported case, provide an earlier usable prerequisite, or admit that it is not yet independent. Do not create fake independence by introducing mocks between every layer.

## Architecture that supports delivery

Start the contract from a consumer example: what does the caller need to do, what result does it observe, and what failure must it handle? State the smallest interface that makes that interaction meaningful. Include state transitions, errors, authorization, retry or idempotency semantics only where the next consumer needs them.

Keep an invariant and the state enforcing it under a clear owner. Hide volatile storage/protocol details rather than spreading them into callers. A useful boundary makes a consumer simpler and allows focused tests without unrelated features; it is not merely a new name around an existing call.

Prefer existing functions, modules and dependencies. Compare plausible alternatives only for a consequential boundary decision, recording why the selected one reduces coupling or uncertainty. No mandatory design tournament. A second implementation, plugin framework or service boundary needs an actual consumer or concrete verification need, not a hypothetical future agent.

An executable contract is an example plus a check that producer and consumer can share. A type definition alone omits runtime semantics; matching mocks may share the same mistake. Version or otherwise identify the contract, and identify who reconciles changes and performs the first assembled probe.

## Fast feedback without weaker evidence

The feedback loop belongs inside each increment, not in a final testing phase. With test-first development, describe the observable failure before the smallest implementation that fixes it; do not plan all imagined tests before any real behavior exists.

| Claim | Smallest credible evidence | Does not establish it |
| --- | --- | --- |
| Calculation/library behavior | Public API call with literal expected values and relevant invalid inputs | Import succeeds or internal collaborator was called |
| CLI/file behavior | Invoke the actual command on disposable files; assert exit status, output and preserved data | Testing a helper while bypassing argument parsing and I/O |
| Persistence | Write through the real boundary, then read after the required reopen/restart | Same in-memory object returned twice |
| Client/server compatibility | Actual client crosses the actual protocol to the producer | Generated types agree or both sides use one canned fixture |
| Access isolation | Allowed and denied actors exercise the real boundary; rejected writes leave state unchanged | Presence of an authorization helper in source |
| Failure safety | Controlled failing operation, observed error and preserved/consistent state | Happy path plus an unexecuted rollback paragraph |
| Performance | Named workload, environment, metric and justified threshold/baseline | More workers, fewer lines or elapsed time from unlike runs |

A local fixture can validate logic; a service sandbox can validate that service's sandbox behavior. Neither proves an unavailable production boundary. Record partial evidence honestly and keep the remaining criterion gated. Never use live customer data, paid endpoints or destructive probes merely to avoid a mock.

Reuse project checks and lightweight disposable resources. Isolate only the resources that can conflict. One focused regression per behavior and relevant integration checks are preferable to repeating every full suite per agent. Requirements may justify wider coverage; there is no universal number of tests or reviewers.

## Existing systems and migration

An existing working path is an asset. Name what must stay true and keep its regression check while adding the next capability. For legacy behavior without tests, a characterization check can be the bounded supporting output for the first changed path, not a demand to test the whole repository first.

A migration plan names the compatibility window, ownership of old/new writes, consistency checks, interruption behavior and rollback or forward-recovery limit. A read-only preview is useful support, but the first migration slice must eventually exercise the real transition on disposable representative data. If dual operation is necessary, give it an exit condition; do not make it a permanent fallback by accident.

Deletion, production rollout and irreversible cutover remain explicit permission gates. Safely preparing or testing a transition does not grant authority to execute it on production.
