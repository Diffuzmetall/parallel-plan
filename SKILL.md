---
name: parallel-plan
version: 1.0.0
description: "Turn agreed outcomes, specifications or existing plans into small working vertical slices, fast feedback and safe parallel work. USE WHEN plan vertical slices OR find the first end-to-end increment OR split a feature or migration OR prepare work for multiple agents OR design handoffs OR rebalance remaining work OR вертикальные срезы OR нарежь план для агентов OR раннее тестирование OR передача работы. Supports one executor or a team. NOT FOR choosing product scope, publishing tracker issues, launching agents, implementing product code, or changing a live runtime."
---

# ParallelPlan

Plan a sequence of useful, verifiable changes to a running system. Optimize time to the first trustworthy result and subsequent feedback, not layers completed, ticket count or worker occupancy. Parallelism is an option, not the definition of success.

Works from agreed requirements or an existing plan; no separate planning skill, tracker, model vendor or agent runtime is required. Use the user's language and the project's terminology.

## Workflow Routing

| Intent | Workflow |
| --- | --- |
| Create a slice plan from agreed outcomes, improve a plan, or replan remaining work | [Prepare](Workflows/Prepare.md) |

## Gotchas

- A slice crosses the boundaries its behavior actually needs, not every layer in the repository. A library or CLI does not need a UI to qualify.
- A completed layer, matching mocks, or a successful build do not prove a working roundtrip. A prototype answers a question; it does not satisfy production acceptance.
- A contract can be ready for a consumer while the component or assembled flow remains unverified. Keep these claims separate.
- A thin slice still owns the authorization, integrity and failure handling needed to make that slice safe. Deferred scope is not deferred data protection.
- A testable architecture need not be a service per slice. Do not create wrappers, plugins or distributed state merely to give agents separate files.
- Requested worker count is a ceiling, not a quota. Ready inputs, shared resources and reviewer eligibility determine useful concurrency.
- A replacement executor does not inherit permissions, active writes or reviewer independence. A historical wait record does not prove current idleness.

## Delivery contract

A usable plan identifies the first real observable result, the later increments that preserve it, original requirement coverage, and a concrete check for each result. Each supporting output names the slice it unblocks. Unknown evidence stays unknown.

For a small solo change, a few slice cards and one verification recipe suffice. Add dependency, ownership and handoff detail only where it affects execution. Do not manufacture a team, a second specification or a mandatory prototype phase.

## Supporting material

Read the selected workflow. It routes to these files only as needed:

- [SliceDesign](SliceDesign.md): splitting choices, meaningful boundaries, architecture and fast feedback.
- [Templates](Templates.md): copyable plan, slice, contract and handoff shapes; omit inapplicable fields.
- [Examples](Examples.md): web, CLI, library, migration and constrained-team examples.
- [WorkerContract](WorkerContract.md): short guidance for an authorized execution handoff.
- [WaitPolicy](WaitPolicy.md): work discovery and bounded idle checks, not an installed scheduler.
- [Integrations](Integrations.md): optional runtime mapping, including DeLM; not needed for ordinary planning.
- [Checks](Checks.md): acceptance cases and evaluation rubric.
- [Sources](Sources.md): retained ideas, conflicts and deliberately excluded machinery.

## Examples

- “Plan the first working increment of this CLI.” → One real input-to-output path, precise evidence and subsequent useful increments; no team ceremony.
- «Подготовь этот план для восьми агентов». → Slice and dependency design, safe startup work and justified active width, not eight overlapping assignments.
- «Передай незавершённый срез другому агенту». → Preserve scope, candidate, evidence, ownership and next action; no automatic reassignment.
- “The release checker is the bottleneck.” → Complementary eligible checks against one candidate, with isolated mutable resources and one evidence aggregator.
