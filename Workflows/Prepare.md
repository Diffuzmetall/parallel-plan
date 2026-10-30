# Prepare a slice plan

## Sufficiency and authority

The agreed outcome, acceptance criteria, exclusions and authoritative source must be identifiable. A clear request can be that source; a separate PRD is not mandatory. Recover answers from available project evidence before asking. Missing product decisions or permissions are blocking questions; routine reversible implementation choices can be labelled assumptions. If only a vague ambition exists, identify the missing outcome instead of inventing a product backlog.

For long-running or multi-executor work, identify the agreed revision or a bounded snapshot of the source requirements, not only a mutable link. A material source change requires reconciliation with its decision owner and a replan of affected work; it does not silently authorize new scope. A stable conversation reference can suffice for a short task; no separate manifest or mandatory hashing is required.

Ground the plan in current entry points, module boundaries, tests and relevant architectural decisions when source access exists. Distinguish observed facts, inherited decisions and proposals. Without source access, label paths and commands as proposed and name what must be confirmed; do not invent executable commands or claim implementation readiness.

For a live team, also establish current owners, claims, unresolved failures, candidate revisions and allowed participants. Without fresh execution state, recommend a work design, not live assignments or claims that someone is idle. Preserve frozen run inputs and unrelated work.

## Done deliverable

Produce a slice section in the canonical plan, or a clearly linked companion when replacing the plan was not requested. Plain chat is sufficient for an explanation. Preserve every original criterion and the existing tracker; use planning IDs until real issue IDs exist. No task creation, agent launch, publication, runtime change or extra spending follows from this workflow.

Use [Templates](../Templates.md) when a concrete artifact is useful. The minimum deliverable is:

- **Goal capsule:** observable outcome, source requirements, invariants, non-goals, authority and assumptions.
- **Slice sequence:** first runnable result and later useful increments; each includes behavior, necessary boundaries, prerequisites, exclusions and verification. Supporting work has a named consuming slice and bounded exit condition.
- **Coverage:** each original criterion maps to a slice/check or an explicit unresolved gate. Criteria and standing project quality requirements both apply. A task summary never replaces the original requirement.
- **Next executable frontier:** what can start with existing inputs, what needs a decision, and what evidence will make the next work ready.

For multiple executors or separately delivered components, add only the applicable detail:

- **Dependency map:** data, contract, integration, permission and shared-resource constraints. Explain real blockers separately from a preferred product demonstration order. Check prerequisite and parent/output-completion edges together for cycles, and check that ownership rules leave an eligible executor able to claim the next output.
- **Concurrency map:** nonconflicting ready outputs at startup and after useful handoffs; owned writes, shared build/test resources and reviewer eligibility. Recommend an active width, not a speedup claim.
- **Handoff contracts:** producer, consumer, minimal interface, earliest usable artifact, evidence level and integration owner. A consumer must have enough information to continue without rediscovering the whole design.
- **Milestone acceptance:** complementary checks on one identifiable candidate, isolated mutable resources, author exclusions when independence is required, and one evidence aggregator.

## Slice design and feedback

Read [SliceDesign](../SliceDesign.md) when selecting the first slice, splitting a broad feature, judging architecture boundaries or planning migration/integration work. Use [Examples](../Examples.md) when a concrete analogue resolves a question; do not read every example routinely.

The first walking skeleton is the smallest meaningful real action through the intended entry point to an observable result. Name the actual boundaries exercised, how to run/check it, and its exclusions. Extend an existing working path rather than rebuilding a ceremonial hello-world. Later slices preserve its regression check.

Integration belongs at early usable handoffs, not at a final "connect everything" phase. A consumer may develop against an agreed contract before the producer is complete, but fixtures remain provisional until the real roundtrip passes. A support artifact may be complete while product acceptance stays open.

For each result, choose the cheapest check that proves the claim, not merely the cheapest check. State setup, action, expected observable outcome and evidence location; identify simulated or unavailable boundaries. Put risk-relevant failure checks in the slice that introduces the risk. Reuse valid baseline evidence; rerun affected checks when the candidate changes.

## Useful parallelism

Size work by its first independently usable and verifiable output, not by file count, hours or desired ticket count. One huge producer can block every consumer; tiny fragments can cost more to coordinate than to implement. Give near-term work executable detail and later slices behavior/coverage detail; refine them when evidence makes their design concrete. Once implementation is separately authorized, a ready first slice need not wait for a fully detailed task graph or a task for every worker. Authorized executors can refine missing work at handoffs without routing every decomposition decision through one permanent planner; original criteria and active ownership remain intact.

Seed a real end-to-end path early, then widen work around verified boundaries. Independent fixtures, contract examples or testability work may begin alongside it when they have a named consumer. Do not hold all useful work behind the skeleton, or pretend speculative work is already integrated.

One writer owns coupled shared-file changes. Consumers may work against agreed boundaries in disjoint paths, with small integration edits explicitly assigned. Readers may share immutable files; tests writing databases, caches, ports or build outputs need isolation or serialization. Worktrees alone do not isolate external resources. Do not add architectural layers merely to manufacture lanes.

Name the dependency chain currently limiting the next useful delivery and how it could shorten: an earlier contract, smaller slice, isolated resource, or resolved decision. If durations are unknown, do not invent a numerical critical path. Match active workers to useful ready outputs and real capacity, not a requested headcount quota.

## Handoffs, continuity and replanning

A parent groups scope and acceptance; holding it is not useful work by itself. If splitting retains its claim and the protocol allows only one unfinished claim, plan the checkpoint and safe release before its owner takes a child. Do not mark an incomplete parent complete to free the executor. An acyclic graph can still stall when every eligible executor holds a bookkeeping parent.

Read [WorkerContract](../WorkerContract.md) for an execution handoff. Prefer ready work near an executor's current context, but allow a checkpointed switch when blocked or finished. A domain preference is neither exclusive ownership nor additional authority. Never relabel an author's self-check as independent review.

A handoff distinguishes **contract-ready**, **component-verified** and **integrated**. These are evidence labels, not a new task-state machine. Use the project's statuses and record exactly which claim passed, on which candidate, with which fixtures. Changed contract semantics must be reconciled with affected consumers before old PASS evidence can be reused.

Name the output and evidence that actually make each consumer ready. Record a usable output's completion through the existing task protocol, or explicitly in the plan when there is no tracker. A progress message is not completion, and completing a contract output does not complete its producer's remaining scope or parent.

A confirmed relevant failure invalidates the affected readiness even if an older completion record remains. Keep the blocker visible to dependent consumers until the responsible owner records an explicit correction/resolution linked to the failure and the affected checks pass on the identified corrected candidate. A message saying "fixed" is insufficient. Preserve failure history and independent work; no new status machine is required.

Replanning preserves completed evidence and active ownership. Record the triggering change, affected slices/criteria, still-valid evidence, invalidated checks, changed prerequisites and next frontier. Checkpoint and stop conflicting writes before a claim/lease transfer. Do not replace an entire backlog because one assumption failed.

Read [WaitPolicy](../WaitPolicy.md) only for idle-work discovery or wait design, and [Integrations](../Integrations.md) only when a concrete runtime mapping is requested. A plan or prompt does not install persistence, timers or wakeups.

## Milestone acceptance

A meaningful milestone may have complementary checks for behavior, authority, recovery, concurrency, clean setup or usability. Select checks because they cover actual risks, not to fill a fixed number of lanes. Independent checks depend on candidate readiness; parent acceptance depends on their results, never the reverse.

Each check names its candidate, criteria, resources and eligibility. Share one expensive baseline where valid. The aggregator may own a disjoint eligible check, then reconcile the union of evidence and gaps. A failure goes to its owner with a reproduction; affected evidence must follow the corrected candidate. No moving-target acceptance, reviewer per microtask or unqualified mixing of old and new receipts.

## Optional specialists and acceptance

The skill is self-contained. When a concrete gap warrants a specialist, use a relevant available capability for architecture, prototypes, tests or diagnosis. Load its body and needed references before applying it; catalogue metadata is not evidence of use. An unavailable specialist does not block ordinary planning and never grants permission to install or launch anything.

Challenge the plan against relevant cases in [Checks](../Checks.md). Report actual evidence separately for structural validation, manual planning samples, independent evaluation and product execution. A well-formed plan is not proof the product works. Stop when the requested plan is executable at its next frontier and material open gates are visible; repeated polishing without a changed finding is not progress.
