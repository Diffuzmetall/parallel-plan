# Representative acceptance cases

These are planning fixtures, not claims of an executed model benchmark. Use the cases relevant to the input and retain the produced plan/evidence. A keyword check alone is not a behavioral evaluation.

| Case | Input | Required outcome | Failure |
| --- | --- | --- | --- |
| Layer-first backlog | Infrastructure, entire schema, entire API, then client integration | First real user/operator roundtrip with a run/check recipe; only its required groundwork; subsequent slices extend that working path | More tickets but no working vertical result until the end |
| Fake first slice | UI and API mocks pass while persistence is required | Name the missing real storage/protocol boundary and keep its criterion open | Call a stubbed demonstration integrated or durable |
| Prototype confusion | Interaction or state semantics are uncertain | One bounded prototype question, captured decision, then a real slice and regression check | Treat throwaway shortcuts as production completion or prototype known behavior routinely |
| Excessive modularity | Only one implementation exists; agents propose plugin adapters and separate services | Cohesive ordinary modules with explicit behavior and a real consumer | Add a framework or service per task merely to enable parallelism |
| Risky thin slice | First runnable action can expose private data or overwrite a value | Relevant authorization/data-loss checks belong to this slice | Defer safety to final hardening because the slice is small |
| Necessary foundation | A real storage change cannot be bypassed | Bounded prerequisite, named consuming slice and earliest end-to-end probe | Pretend no groundwork is needed or build a general platform first |
| Existing walking skeleton | A real product path is already verified | Extend that path with the next authorized behavior | Restart with an unrelated hello-world to satisfy the method |
| Useful parallel work | Approved service, SDK and three clients; stable minimal API exists | Independent client/output boundaries with early roundtrip handoff and real integration gate | All clients wait for the whole service, or invented APIs are called ready |
| False eight-way width | Eight agents requested; all proposed changes rewrite one shared module | Explain the conflict, retain one writer, expose useful disjoint work or recommend a smaller active team | Eight overlapping writer assignments or filler work |
| Milestone fan-out | One actor checks a release while three qualified peers are free | Complementary checks on one candidate; isolated test resources; one evidence aggregator | One opaque check-everything task, or identical full suites run four times |
| Dependency cycle | Parent acceptance waits on check outputs | Checks depend on candidate readiness; parent depends on check outputs | A check also depends on parent acceptance |
| Soft specialization | Backend-preferring actor finishes its work; eligible client work exists | Preserve checkpoint and choose useful ready work without permanent role restriction | Idle because it is not a backend task, or context switch every turn |
| Independence | The only free actor authored the code under review | Report eligibility limit; use another qualified peer or keep gate open | Relabel self-review as independent acceptance |
| Eight-hour session | Compacted worker must create new tasks | Resident short contract plus current task/criterion/skill recovery at a safe boundary | Reliance on an old bootstrap message or unconditional full-document rereads |
| Sticky named wait | Free actor watches one large unfinished task; other work becomes ready | Work-event reevaluation with safe wait reconciliation and atomic claim | Treat unrelated ready work as completion of the named dependency |
| Quiet board | Ten minutes pass; no eligible work and a human gate is unresolved | No model polling or invented activity; explicit reason and preserved gate | Periodic wake storm or automatic permission escalation |
| Weak skill evidence | Catalogue contains a skill; history access fails | Mark availability verified and historical use unknown | Claim loaded, unused or applied from the catalogue alone |
| Candidate changes | One parallel check finds a real defect | Owner correction; affected checks use the new candidate; unaffected reuse is justified | Combine old and new PASS receipts into one unqualified acceptance |
| Existing live work | Fresh board already has relevant claims and DONE evidence | Reuse existing results; propose only missing outputs and preserve owners | Duplicate tasks or rewrite frozen run inputs |

## Worked example — manual planning sample, not an executed product test

Input: an approved item editor must create/reopen an item, edit it with validation and preserve its previous value if a save fails. The initial plan builds all storage, all endpoints, all screens, then integrates them.

A conforming replacement has a real first slice: create and reopen one item through the intended entry point and actual API/storage on disposable resources. Its evidence must demonstrate the returned value survives the required reopen boundary; unrelated list/search capabilities are not invented. The next slices extend the same route with validated edits and safe failure behavior, retaining the first roundtrip regression.

While the first slice is built, other eligible actors can prepare a contract example and failure fixtures or inspect testability without writing the owner's coupled files. Those outputs prove only their own scope. After the candidate is available, separate peers can check persistence, validation/failure behavior and clean setup on the same candidate using isolated state; one aggregates the evidence. Four actors do not require four simultaneous writers of the storage module.

Counterexample verdicts: "all schema tasks are DONE" does not prove the first slice; a canned success response does not prove storage; a prototype with memory-only state can resolve interaction design but not the persistence criterion. A contract update requires affected consumer/check owners to reconcile it before their old PASS evidence is reused.

## Routing examples

Should select this skill: «переделай план так, чтобы 8 агентов могли работать независимо»; "split the final milestone into parallel acceptance outputs"; «перепланируй оставшуюся работу, сохранив роли как предпочтение».

Should not select this skill by itself: "deploy this release"; «запусти восемь агентов»; "fix a failing parser"; «создай задачи в трекере по готовой раскладке». Those require their own authorized execution workflow.
