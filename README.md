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

## Real examples, with the actual plans

[Examples.md](Examples.md) follows two real projects from requirements through delivery and recorded evidence:

- **pi-durable-host:** staged backend/client delivery, then a revised migration route without BB. Import and restricted restore passed, but actual continuation remained blocked: the migration verdict stayed **NO-GO**.
- **pi-durable-delm:** an early ABI contract unblocked consumers before the adapter was finished. A separate frozen review input avoided an acceptance/reviewer dependency cycle; a faulty removal assertion required a measured correction before final acceptance.

The original published [host plan](HostPlan.md) and [DeLM plan-report](DeLMPlan.md) are included as commit-pinned snapshots, in their original Russian. The worked analysis is in English. These are historical cases, not invented demonstrations or proof that this skill caused the outcomes.

The transferable pattern is a usable early output, an explicit consumer, a real assembled check and honest remaining gates—not these projects' runtime, tracker or actor count.

## Package map

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Discovery metadata, entry point, scope, and gotchas |
| [Workflows/Prepare.md](Workflows/Prepare.md) | The planning workflow and deliverable contract |
| [SliceDesign.md](SliceDesign.md) | Splitting choices, architecture boundaries, and evidence |
| [Templates.md](Templates.md) | Adaptable plan, slice, contract, and handoff shapes |
| [Examples.md](Examples.md) | Source-backed host and DeLM cases, checks, outcomes and limitations |
| [HostPlan.md](HostPlan.md) | Archived published host plan, with pinned upstream links |
| [DeLMPlan.md](DeLMPlan.md) | Archived published DeLM plan-and-execution report |
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

[Checks.md](Checks.md) contains representative scenarios, not an executed model benchmark. [Examples.md](Examples.md) analyzes real plans and recorded product evidence; those product checks were not rerun for this documentation. Structural checks, link validation and historical case studies cannot establish that this skill improves model outcomes. No measured speedup or behavioral-evaluation result is claimed.

## License

[MIT](LICENSE). Referenced upstream projects retain their own licenses.

## Attribution

This package synthesizes planning principles into a standalone workflow. [Sources.md](Sources.md) records influences and deliberately excluded machinery. The two source-plan snapshots identify their original repositories, commits and MIT licenses; they bundle documentation only, not those projects' runtimes or private execution inputs. Other referenced tools and skills are not bundled or required.
