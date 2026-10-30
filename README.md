# parallel-plan

An agent skill for turning agreed requirements into small working increments, early feedback, and safe parallel work.

Start with one real end-to-end result. Extend it without breaking what already works. Add parallel workers only when their inputs, write boundaries, and verification allow it.

**Use it with one executor or a team.** No Planning skill, DeLM runtime, Pi installation, issue tracker, model provider, or other skill is required.

## What you get

- A first runnable slice and a sequence of useful increments.
- A mapping from the original requirements to slices and concrete checks.
- Explicit prerequisites, unresolved decisions, and work that can start now.
- Where needed: ownership boundaries, producer–consumer contracts, handoffs, and independent milestone checks.

A slice crosses the boundaries its behavior needs. A CLI does not need a UI; a library does not need a database. A finished layer, a mock response, or a successful build is not proof of an integrated product.

## Install

Clone this repository into a skill directory supported by your agent, using `parallel-plan` as the directory name. For agents that discover the shared `~/.agents/skills` directory:

```sh
git clone https://github.com/Diffuzmetall/parallel-plan.git ~/.agents/skills/parallel-plan
```

If your agent uses another skill root, clone there instead. Keep the entire repository together: `SKILL.md` links to the included workflow and reference files. Reload skills or start a fresh session as required by your agent.

If an older copy named `ParallelPlan` or `parallel-plan` is already installed, reconcile it first. Do not overwrite local changes or leave two copies declaring the same skill name.

This is an instruction package, not an executable. There are no dependencies to install, daemons to start, or credentials to configure. Discovery and invocation syntax depend on the host agent.

## Use

Ask your agent to use **parallel-plan** and supply your agreed requirements or existing plan:

> Use parallel-plan to replace this layer-first backlog with working vertical slices. Keep the original acceptance criteria. Identify the first real roundtrip and how to verify it.

> Prepare this plan for up to four agents. Identify independent work, shared-file conflicts, early handoffs, and milestone checks. Do not create issues or launch agents.

> Replan the remaining migration after this contract change. Preserve completed evidence and current owners; name the checks that are now invalid.

For a small solo change, the output can be a few slice cards and a verification recipe. Team coordination detail is conditional, not mandatory ceremony.

## Example: an item editor

Instead of:

```text
all database work → all API work → all screens → integration → tests
```

Plan:

1. An authorized user creates and reopens one private item through the real entry point, API, and storage. Verify persistence and access isolation.
2. The owner edits that item with validation. Keep the first roundtrip working.
3. A failed edit preserves the last saved value and the unsaved draft. Verify failure and recovery on disposable state.

Each increment includes the safety checks its behavior requires. Later recovery work is not permission to ship corrupt writes in the first increment.

Consumers can start against an agreed contract before the producer is complete. Their fixture results remain provisional until the real integration passes. See [Examples.md](Examples.md) for CLI, library, migration, and constrained-team cases.

## Package map

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Discovery metadata, entry point, scope, and gotchas |
| [Workflows/Prepare.md](Workflows/Prepare.md) | The planning workflow and deliverable contract |
| [SliceDesign.md](SliceDesign.md) | Splitting choices, architecture boundaries, and evidence |
| [Templates.md](Templates.md) | Adaptable plan, slice, contract, and handoff shapes |
| [Examples.md](Examples.md) | Worked planning examples |
| [Checks.md](Checks.md) | Acceptance scenarios and failure cases |
| [WorkerContract.md](WorkerContract.md) | Optional guidance for an authorized execution handoff |
| [WaitPolicy.md](WaitPolicy.md) | Optional work-discovery design; not an installed scheduler |
| [Integrations.md](Integrations.md) | Optional mappings to files, trackers, and agent runtimes |
| [Sources.md](Sources.md) | Design influences and attribution boundaries |

## Boundaries

The skill plans delivery. It does not choose product scope, create tracker issues, launch workers, implement code, install scheduling, spend money, or deploy a release. Those actions require separate authorization and tools.

The existing specification and acceptance criteria remain authoritative. Keep one canonical plan and the project's existing task state. Distinguish **contract-ready**, **component-verified**, and **integrated** evidence; these labels do not create a new task-state machine.

A plan describes checks to perform. It does not prove that the product works. Self-review is not independent acceptance.

## Validation status

[Checks.md](Checks.md) contains representative scenarios, not an executed model benchmark. [Examples.md](Examples.md) contains illustrative plans, not executed product tests. Structural checks and link validation cannot establish that a skill improves model outcomes. No measured speedup or behavioral-evaluation result is claimed.

## License

[MIT](LICENSE). Referenced upstream projects retain their own licenses.

## Attribution

This package synthesizes planning principles into a standalone workflow. [Sources.md](Sources.md) records influences and deliberately excluded machinery. Referenced tools and skills are not bundled or required; no rights to their separate content are granted by this repository.
