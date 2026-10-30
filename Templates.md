# Copyable output shapes

Adapt these to the project's canonical document or tracker. Keep stable requirement references; do not create a second task-state store. Omit irrelevant fields rather than filling them with ceremony. Examples and future checks are proposals, not completed evidence.

## Minimal plan

```markdown
# <Outcome> — slice plan

## Goal and boundaries
Outcome: <observable change for a user/operator>
Source: <request/spec/criterion references>
Already works: <verified path and evidence, or unknown>
Preserve: <invariants and fixed decisions>
Excluded: <non-goals>
Authority: <allowed work and explicit gates>
Assumptions / blocking decisions: <only material items>

## Slices
<Cards below, in useful delivery order>

## Coverage
| Original criterion | Slice/check | Evidence required | Open gate |
| --- | --- | --- | --- |
| <reference> | <planning ID> | <observable proof> | <none or blocker> |

## Next frontier
Ready now: <outputs with existing inputs>
Blocked: <exact missing output, decision or access>
Next useful delivery: <observable result and why this comes first>
```

## Slice or supporting-output card

```markdown
### S1 — <user/operator can do something>
Kind: <behavior / supporting output / experiment / check>
Outcome and consumer: <what becomes possible, for whom>
Requirement coverage: <original IDs; no new product scope>
Path exercised: <entry point → actual boundaries → observable result>
Prerequisites: <specific usable outputs, not whole departments>
Scope / excluded: <smallest safe complete case / later cases>
Verification: <setup; action or confirmed command; expected result; evidence location>
Preserves: <existing regression and new risk-relevant negative check>
Open gate: <authority, unknown contract, unavailable service, or none>
```

For a supporting output, replace the path with the named consuming slice and an exit check. For an experiment, name one question and the decision its result enables; no production acceptance credit. For a check, name the candidate and claimed criteria. No fabricated repository commands: mark a future test command as proposed until confirmed.

## Team additions

```markdown
## Dependencies and concurrency
Edges: <output A → output B; reason for each edge>
Critical chain: <what currently limits the next delivery; no invented durations>

| Frontier | Ready outputs | Write owners/paths | Shared resources | Useful active width |
| --- | --- | --- | --- | --- |
| Startup | <IDs> | <exclusive boundaries> | <isolation or serialization> | <justified number> |
| After <handoff> | <IDs> | <boundaries> | <resources> | <number> |

## Ownership and acceptance
Integration owner: <owner of assembled behavior, not a permanent planner>
Role preferences: <current context, alternative eligible work, switching checkpoint>
Milestone checks: <candidate; criteria; resources; reviewer eligibility>
Evidence aggregator: <owner who reconciles receipts and gaps>
```

A plan may have several ready outputs but fewer available qualified executors. Report both; never infer a live assignment from a proposed owner label. For one executor, omit this section unless resource conflicts or external handoffs still matter.

## Producer–consumer contract

```markdown
Contract ID/revision: <stable reference>
Producer / consumers: <owners and near-term slices>
Operation: <input → output example>
Semantics: <errors, state, authority and retries relevant to this operation>
Shared check: <fixture/assertion usable against the real producer>
Earliest handoff: <artifact the consumer can actually use>
Still provisional: <simulated or unavailable boundary>
Integration owner/check: <who assembles the real path and how it passes>
Change rule: <affected consumers notified; incompatible evidence rechecked>
```

## Handoff or recovery checkpoint

```markdown
Task / source criteria: <references>
Delivered artifact: <path/ref and exact revision or content identity>
Evidence level: <contract-ready / component-verified / integrated; name the claim>
Verified: <check → actual outcome → evidence reference>
Not verified: <remaining boundaries, failures and blockers>
Changed paths/resources: <owned writes; running processes; dirty state if relevant>
Ownership: <current claimant; transfer/release status; do not assume stopped>
Next consumer/action: <who can do what with this artifact now>
Recheck if: <contract/candidate/resource condition invalidating evidence>
Permissions and gates: <unchanged constraints; decisions still needed>
```

A hash or SHA identifies content; it is not test evidence. Uncommitted work needs an identifiable patch/artifact snapshot, not just the branch name. The receiving executor reconciles live ownership before writing.

## Replan delta

```markdown
Trigger: <new evidence or changed requirement>
Affected: <slices, original criteria, owners and consumers>
Retain: <completed work and still-valid evidence, with reason>
Invalidate: <affected checks or assumptions>
Change: <smallest corrected sequence/contract/dependency set>
Next frontier: <ready work and remaining gates>
```
