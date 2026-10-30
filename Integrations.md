# Optional execution-system mappings

The planning method requires none of these systems. An integration maps output cards and evidence into an existing authorized workflow; it does not enlarge permissions, install dependencies or certify runtime behavior.

## Plain files or an issue tracker

Keep the existing source of requirements and task state. A project without a tracker can use one plan document. A project with a tracker can link slice cards to real issues when issue creation is separately requested. Do not maintain competing checklists that each claim to be authoritative.

Map prerequisites to native dependency links, owners to actual claims, write boundaries to the existing reservation mechanism, and checks to evidence attached to the relevant work. Labels such as contract-ready describe evidence, not extra mandatory tracker statuses.

## Native agents

Pass a bounded slice brief with source criteria, write scope, inputs, permissions, expected output and verification. A launch receipt means admitted work, not accepted output. Confirm the exact runtime's ownership, stop and result semantics before reassignment. No fixed number of agents, nested delegation, recurring polling or particular model provider is required.

A candidate can be a commit, artifact digest or reproducible snapshot of uncommitted work. Reviewers need the exact content under test; a moving branch name is insufficient. Use existing sandbox/resource controls rather than asserting that a read-only brief enforces a sandbox.

## DeLM mapping

This is a conditional mapping, not proof that the current runtime exposes these calls. Inspect the loaded tool schema before use.

- A free actor discovers eligible work with `delm_wait(action=work, reason=...)` without items where that contract is supported.
- An actor retaining a blocked claim waits for exact existing dependency IDs with `action=wait`.
- Work availability does not mean those dependencies succeeded. A switch still requires checkpointing and safe claim/resource transfer.
- Inspect saved wait and delivery state before replacement or cancellation; committed wake delivery cannot be assumed retractable.
- Keep frozen run inputs and the current authority surface intact. Planning changes do not hot-patch a live team.

Feature support comes from the exposed schema and runtime evidence, not inferred ordering of build-name strings. See [WaitPolicy](WaitPolicy.md) for the runtime-neutral invariants.

## Unsupported capabilities

Without atomic claims or file reservations, propose serial ownership of conflicting writes rather than pretend coordination exists. Without durable prompt injection, use explicit checkpoint recovery. Without service access, record partial evidence and keep real integration open. Missing automation is not permission to install it.
