# Real plans and worked cases

These cases come from **pi-durable-host** and **pi-durable-delm**, not fictional applications. They show actual requirements, delivery stages, handoffs, failures and recorded results. The analysis connects those decisions to ParallelPlan; it does **not** claim that these projects used this version of the skill, that the skill caused their outcomes, or that parallelism produced a measured speedup.

The source plans are included, not just linked:

| Project | Included source | Evidence boundary |
| --- | --- | --- |
| pi-durable-host | [HostPlan.md](HostPlan.md): published revised plan at `c0019d73152b58783d1b74fabe95f6982206aa55` | Historical P0–P5 delivery and a separate, still NO-GO migration milestone |
| pi-durable-delm | [DeLMPlan.md](DeLMPlan.md): published plan-and-execution report at `6814eeb9268b87d719b6be0d076267d70c565990` | Actual N14 tasks, handoffs, correction, independent acceptance and source publication |

These are archived **published** documents, not the original private frozen execution inputs. They retain the original Russian and stage identifiers; relative links point to the pinned upstream commits. They are references, not additional canonical plans or permission to resume those projects.

All product results below are **recorded historical evidence** inspected for this documentation update. No product suite, migration, live model or runtime was rerun. Private transcripts, credentials and machine-specific execution plans are not bundled. Pi, DeLM, four actors and their task system are properties of these examples, not dependencies of this skill.

## A. pi-durable-host: deliver clients around one real execution owner

### Agreed outcome and constraints

Keep the existing backend/SDK and native Durable 1.4 execution/recovery owner. Make the terminal, BB integration and iii client use that owner rather than introducing another runtime or queue. Preserve exact saved model/profile identities, authenticated admission, canonical retries and independent installation. A working client must be demonstrated through its actual entry point, not inferred from compilation.

### The actual staged plan

The historical acceptance sequence was **P0 → P1 → P2 → P3 → P4 → P5**, followed by a separately bounded P6 transition. These are the source plan's stages, not new tickets invented for this example.

| Original stage | Requirement and usable result | Check and evidence boundary |
| --- | --- | --- |
| P0 | One native owner; explicit profile and saved model IDs | Incompatible profile/model refuses before resume; no silent model substitution. This establishes the execution boundary before client expansion. |
| P1 | Authenticated HTTP/SSE/SDK with canonical receipts | Retry, conflicting payload, cache expiry, crash and reopen preserve the intended execution; authorization and private-diagnostic regressions are checked. |
| P2 | Independently installable host and configured native composition | Real configured tools, guards, memory, Goal and schedules; standalone packages do not acquire another adapter or a private installation dependency. Configured compatibility is not arbitrary-plugin compatibility. |
| P3 | The existing terminal works as a remote client | Actual installed TUI/PTY checks cover editor, navigation, tools, interrupt, detach, reconnect and new session. A successful typecheck is not terminal acceptance. |
| P4 | BB thread/child binding, controls, history and standalone bridge | Actual isolated Core/Chrome behavior on the exact compatibility overlay. An unexplained initial UI timeout remains disclosed; `/compact` is unsupported. |
| P5 | Signed delegated iii work through the same native owner | Actual local engine/SDK and installed native faux host: retry, control, recovery and immutable answer reference. The iii-only installation is checked separately. |
| Offline P6 | Bounded backup/restore and rollback preparation | Only a disposable closed-owner same-version rehearsal in this historical slice. It did not prove migration of a selected real session or cross-version recovery. |

This was not “finish every backend feature, then build three empty frontends.” Each stage had an observable result and its own checks. The later clients reused the established owner/receipt boundary, while their UI or transport-specific behavior still needed acceptance.

**A concrete vertical slice:** P3 crosses terminal interaction → SDK → backend/native owner → returned state. The installed PTY is the consumer check. Its outcome is a functioning remote terminal, not merely a controller module. P4 and P5 extend the system with different real consumers; they do not retrospectively make an untested P3 usable.

### What the recorded delivery actually established

The pinned [status report][host-status] records **51 PASS / 2 PARTIAL** against 53 original criteria for the historical scope. It distinguishes source tests, installed packages, actual PTY/Core/engine checks and reused evidence on unchanged bytes. That aggregate does not remove the disclosed BB timing failure or establish production readiness.

The plan also keeps source publication, package release, deployment and data migration separate. A published repository is not evidence that a user's working installation was safely replaced.

### Replan: remove BB from the current critical path without calling it fixed

The later authorized milestone changed to **backend + SDK + terminal + actual local iii, without BB**, using one protected copy of a selected inactive session. The revised plan retained BB's unfinished checks and defect as deferred work; it did not erase them or keep them as an irrelevant blocker.

Its real acceptance requirements were:

1. Validate the definitions actually saved in the session before auto-resume.
2. Import without changing native identities, history, tasks, documents, children or pending state; never silently remap the model.
3. Demonstrate actual controlled continuation without replaying old actions. Label static or simulated checks separately.
4. Demonstrate terminal and local iii against one backend, including reconnect, interrupt, recovery and canonical retry, without BB.
5. Restore from the untouched original backup on a separate copy using the exact source runtime/profile.
6. Obtain independent candidate-bound evidence and an outgoing review before publication.

This is a scope/dependency correction, not a new architecture. Already-valid unchanged evidence remains useful; newly imported real state requires its own proof.

| Actual checkpoint | Recorded result | What it did not unblock |
| --- | --- | --- |
| Protected snapshot and import | Original preserved; actual import retained native records and artifacts | Import success alone did not permit an execution/continuation claim. |
| Generated terminal/iii canary | Actual PTY and local engine checks passed | A generated faux session was not the selected real session. |
| Separate original-runtime restore | Restricted rollback passed | No restoration of production authority or permission to activate the candidate. |
| Actual candidate startup | Saved model availability was checked and refused before native session factory/resume because credentials were unavailable | No model remap, credential access or substitute faux continuation was allowed to turn this into PASS. |

**Recorded result: migration NO-GO.** The [selected-copy report][host-pilot] distinguishes the successful import, generated canary and restricted restore from the blocked actual continuation. Private proof locators and payloads are withheld; this public report is not a self-contained reproduction of that private pilot.

**Portable lesson:** replan the remaining path around the approved outcome, not around stale dependencies. A successful supporting output can unblock another bounded check without satisfying the final outcome. A real refusal may be the correct safety behavior while the requested transition remains incomplete.

## B. pi-durable-delm: make an early contract useful before the producer is finished

### Agreed outcome and constraints

Deliver the portable DeLM package into the **actually installed Native 1.4 host**, retaining its loader, admission controller, guards and execution owner. The previous HOST05 proof used Native 1.0.2 with a disclosed API patch; it could not establish current-host compatibility.

The accepted scope used the existing four actors and disposable fixtures, ordinary terminals, and deterministic faux model requests. It did not authorize replacing Native, adding a second Harness, reloading the live team, making live/paid model calls or treating source publication as deployment.

### Actual outputs, owners and handoffs

The [included plan-report](DeLMPlan.md) preserves actual task IDs and DONE event numbers. Here is the part needed to understand the slicing:

| Original output | Owner | Actual handoff / verification |
| --- | --- | --- |
| N14-ABI, DONE 792 | Bob | A usable actual-host contract reached Carol and Alice before Bob finished N14-ADAPTER at DONE 834. Contract readiness was not adapter acceptance. |
| N14-FIXTURE, DONE 804; N14-FIXTURE-INTEGRATION, DONE 825 | Dave | Actual-host MODEL-only fixture, then board/wake/reopen integration support; these were separate useful outputs, not progress notes inside one large task. |
| N14-LAUNCH, DONE 839 | Carol | Portable skill and ordinary-terminal entry path; a terminal manager was not required. |
| N14-PACKAGE, DONE 854; N14-ARCHIVE-OUTPUT, DONE 860 | Alice | Packaging/setup map and the exact immutable v2 archive for the installed acceptance run. |
| N14-FINAL-REVIEW-INPUT, DONE 874 | Dave | Frozen candidate/evidence input made available while final acceptance was still open. |
| N14-FINAL-UI-REVIEW, DONE 906; N14-FINAL-REVIEW, DONE 914 | Carol; Alice | Complementary independent UI and source/evidence checks, including the measurement correction below. |
| N14-ACCEPT, DONE 918 | Dave | Final evidence index after both independent reviews and correction resolution. |
| N14-PUBLISH, DONE 923 | Alice | Separate source delivery after acceptance; not an effect inferred from an assistant's progress report. |

**Condensed dependency view from the recorded handoffs, not a complete board export:**

```text
N14-ABI ──> adapter, launcher and packaging work
N14-FIXTURE ──> fixture integration

finished runtime + launcher + packaging ──> immutable archive
archive + fixture integration ──> installed checks / frozen review input
review input ──> independent UI and source/evidence reviews
accepted reviews + resolved finding ──> acceptance ──> publication
```

The parallelism came from different usable outputs and write boundaries, not four people editing the same integration. Common files changed through sequential handoffs; the Git index had one publisher. The actors did not launch a new reviewer team for each small task.

### The deadlock avoided by splitting an early output

If reviewers wait for final acceptance to be DONE, while final acceptance waits for their review, nobody can finish. The producer therefore published **N14-FINAL-REVIEW-INPUT** separately. Reviewers consumed the frozen candidate, not a claim that the entire acceptance was already complete.

There was a second constraint: one unfinished claim per actor. Publishing a child output while keeping the blocking parent claim would not solve that ownership problem. The recorded workflow used **release → claim → complete → reclaim**, rather than simultaneously holding both tasks. Another tracker might express this differently; the portable requirement is that the output can actually be owned and completed.

### What the installed slice exercised

The [installed-flow result][delm-flow] records two product-opened ordinary-terminal actors, bootstrap replay, real Native Bash work against the board, event wake/read/explicit ACK, exact pending-wait reopen, cancellation, stop/resume fences, draft preservation and the shipped interactive curses board. The read-only observer did not mutate the board or consume the actor's receipt; quitting it left the backend and Native owners alive.

This crosses the package → actual host loader → advertised tool → board → wake → consumer boundary. A mocked loader or a board mutation performed instead of the actor's real tool call would not establish the same result.

## C. pi-durable-delm: invalidate the wrong evidence, not the whole product

During independent review, Carol found that a post-removal assertion was unsupported. The existing lifecycle result claimed the removed skill was absent from the actual prompt, but a successful assistant response did not prove the required observation had occurred. A soft hook error could coexist with that response.

The source plan's response was not “rerun everything” or “change the product until the test passes”:

| Step | Actual correction | Readiness consequence |
| --- | --- | --- |
| Finding | Retract the unsupported negative-removal inference | That claim could no longer support final acceptance. Other unchanged runtime evidence was not automatically discarded. |
| New output | N14-POST-REMOVE-WITNESS, DONE 896; append-only supplement | Preserve the original candidate/evidence. Measure the **effective current** SDK catalogue, rather than grep the entire preserved history for old skill text. |
| Hard gate | Require an actual measurement and reject five negative cases | Missing record, hook error, count mismatch, active skill and active wait tool must all fail the gate. |
| Independent recheck | Reviewer resolution, UI review and source/evidence review | The correction becomes accepted evidence, rather than the producer declaring the old claim valid again. |
| Final acceptance | N14-ACCEPT after those reviews | Final verdict explicitly depends on the supplement; the original lifecycle flag alone remains insufficient. |

The [hard-gate result][delm-hard-gate] records an accepted actual measurement and all five rejected negative cases. The authoritative [final review index][delm-index] records the retracted claim, replacement measurement, independent reviews and exact archive identity.

**Recorded outcome:** `PASS_LOCAL_CURRENT_INSTALLED_NATIVE14_WITH_EXPLICIT_CORRECTION`, tied to archive SHA-256 `830e43da3e6119fad22507d29db7da0de94fa80817442b26ce4298ca323e7480`. The index correlates 449 installed/extracted files and 37 runtime assets.

The clean pipeline used 17 faux requests; the bounded correction added two. Including the earlier disclosed 17-request attempt, the index records **36 total faux requests, zero live/paid requests**. These are historical counters, not requests made while writing this example. The earlier acceptance prose's pre-supplement count is not the final total.

Live-team reload, live-model quality and fresh-machine public retrieval were not established by that local acceptance. Source publication subsequently occurred as its own task; neither event proves rollout or model effectiveness.

**Portable lesson:** publish a consumer-ready candidate, attach findings to the exact claim they invalidate, keep the original evidence, add the necessary corrective check, and reverify before unblocking acceptance. Do not confuse a green command, a completed producer task or a confident narrative with the missing proof.

## Applying the cases without copying their machinery

Use the existing [templates](Templates.md) to write only the parts your task needs:

- Name a real first roundtrip, as the host plan did for execution and its clients.
- Split a useful early contract or review input when a consumer is genuinely waiting for it, as N14 did.
- Check both dependency readiness and whether someone can own the next output.
- When scope changes, preserve unresolved defects and unchanged evidence instead of relabelling everything DONE.
- When evidence fails, repair and recheck the affected claim before downstream acceptance.

Keep the project's specification and canonical plan authoritative. These archives are learning material, not a reason to copy their actor count, stages, tracker, permission model or runtime into a simpler task.

[host-status]: https://github.com/Diffuzmetall/pi-durable-host/blob/c0019d73152b58783d1b74fabe95f6982206aa55/docs/STATUS.md
[host-pilot]: https://github.com/Diffuzmetall/pi-durable-host/blob/c0019d73152b58783d1b74fabe95f6982206aa55/docs/verification/REAL_PILOT.md
[delm-flow]: https://github.com/Diffuzmetall/pi-durable-delm/blob/6814eeb9268b87d719b6be0d076267d70c565990/evidence/native14/acceptance/installed-flow-result.json
[delm-hard-gate]: https://github.com/Diffuzmetall/pi-durable-delm/blob/6814eeb9268b87d719b6be0d076267d70c565990/evidence/native14/acceptance/postremove-hard-gate-result.json
[delm-index]: https://github.com/Diffuzmetall/pi-durable-delm/blob/6814eeb9268b87d719b6be0d076267d70c565990/evidence/native14/acceptance/final-review-index.json
