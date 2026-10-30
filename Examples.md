# Worked planning examples

These are fictional planning samples, not executed application tests. Paths, commands and interfaces below are illustrative proposals to confirm against a real repository. The examples demonstrate plan shape and evidence requirements; they do not establish measured speedups or model reliability.

## A. Web editor: from layers to a real saved item

**Agreed requirements:** R1 create and reopen a private item; R2 edit with non-empty text; R3 failed saves preserve the previous value. Existing authentication is available. No sharing, search or new authentication system is requested. Four executors are available.

**Before:** complete schema → complete API → complete UI → wire everything → test.

**After:**

| ID | Outcome | Prerequisite | Verification and boundary |
| --- | --- | --- | --- |
| A1 | An authorized user creates and reopens one private item through the minimal page | Existing authentication and disposable database | Browser creates text `alpha`; restart backend; reopen shows `alpha`. Another user cannot read or change it. Simulated write failure produces no false success or partial item. Covers R1 and first-write safety. |
| A2 | The owner edits the item with non-empty text | A1's usable item contract and schema | Edit to `beta`, reopen shows `beta`; empty edit is rejected and leaves `beta`; another user's edit is denied. Covers R2. |
| A3 | A failed edit preserves the last saved value and the unsaved draft | A2's update path | Force a storage write failure on disposable state; UI reports failure, draft remains, reopen shows last committed value. Restore storage and retry the user's draft. Covers R3. |

A1 introduces only the schema and endpoints it needs. A2 may begin consumer implementation once A1's contract is usable, but A2 is not accepted until its real roundtrip passes. A3 adds edit-specific recovery; A1/A2 never knowingly permit corrupt writes while waiting for A3.

**Startup frontier:** one writer owns A1's coupled schema/server/page bootstrap. A second can prepare denied-user and storage-failure fixtures in a separate test-support area after agreeing on the boundary. No four-way implementation width is justified yet; do not invent list/search work for the other executors. After the bootstrap handoff, server and UI work may split on that contract with one named integration owner. At milestone acceptance, eligible peers can check persistence/isolation, edit/recovery and clean setup on the same candidate with separate databases and ports.

**Proposed contract:** `createItem({text:"alpha"}, actor) → {id,text:"alpha"}`; unauthenticated requests are rejected, owner identity is server-derived, success means the transaction committed. The shared check creates then reads by ID through the real producer. UI fixtures may use this shape before the service is ready; they prove neither persistence nor access isolation.

**Handoff example:** contract `item-create/v1`, identified schema patch and API example; **contract-ready**, not integrated. Consumer can build form submission against the fixture. Server owner supplies actual create/read evidence; UI owner owns the browser roundtrip. Any change to error semantics requires both owners to reconcile their checks.

**Next action:** inspect the existing auth/test entry points and implement the A1 probe. Production deployment remains outside authority.

## B. Solo CLI: no UI and no team ceremony

**Agreed requirements:** R1 import a small UTF-8 CSV with `sku,quantity` into a local store and inspect it later; R2 reject malformed rows without partial writes; R3 rerunning the same import does not duplicate records. No server, streaming mode or large-file support is requested.

| ID | Outcome | Prerequisite | Verification |
| --- | --- | --- | --- |
| B1 | Import two distinct valid rows and read them from another CLI process | Existing command framework or the smallest command entry point | Invoke the real import command against a disposable store; exit 0; a second process lists exactly the two expected records. Input validation and one transaction are part of the path. R1. |
| B2 | Malformed and duplicate input has defined, non-destructive outcomes | B1's import boundary | A bad third row exits nonzero with a useful location and leaves the pre-import store unchanged; reimporting the original file leaves two records under the agreed upsert semantics. R2/R3. |

B1's supported domain is explicit; it rejects unsupported input instead of partially importing it. B2 expands and verifies failure/idempotency behavior, not permission to postpone integrity. If upsert versus reject is not agreed, that is one product question before implementation, not a reason to design both modes.

**Proposed probe:** `inventory import sample.csv --store scratch.db`, then a fresh `inventory list --store scratch.db`; compare literal records, not just command success. This command is illustrative, not an assertion that such a binary exists.

**Coverage:** R1 → B1; R2/R3 → B2, with transaction safety already required in B1. **Next frontier:** B1; one executor, no leases, workers or milestone fan-out invented by the plan. **Boundary:** command parsing → CSV parser → real local persistence → fresh-process output.

## C. Library: usable behavior through a public API

**Agreed requirements:** R1 calculate a basket total from nonnegative integer minor-unit prices and quantities; R2 apply a fixed integer-minor-unit discount, floored at zero; R3 reject invalid inputs without mutating the basket. No percentage discounts, taxes, network, database or CLI is requested.

| ID | Outcome | Prerequisite | Verification |
| --- | --- | --- | --- |
| C1 | A library consumer obtains a total for a valid basket | None | Public `total([{price:125,quantity:2}])` returns `250`; invalid inputs are rejected and the input object remains unchanged. R1/R3. |
| C2 | The consumer applies a fixed discount through the same public boundary | C1's price/quantity contract | Discount `50` produces `200`; discount `300` produces `0`; invalid discounts are rejected without mutation. R2/R3; C1 checks retained. |

**Architecture choice:** one cohesive calculation module with a small public operation, not a pricing plugin framework. A consumer invocation is the contract. Implementation helpers may change without changing these tests. No fictitious persistence/UI work is needed to make the slice "vertical".

**Next frontier:** C1, followed by C2. One implementation owner suffices; a separate consumer may prepare examples against the agreed signature if there is actual concurrent demand. Performance benchmarking is not an invented acceptance gate.

## D. Legacy migration: a bounded real transition

**Agreed requirements:** R1 migrate existing saved records from format v1 to v2 without changing visible values; R2 interruption must not corrupt the original, and retry must be safe; R3 the old reader remains usable until explicit cutover approval. Production writes and deletion are not authorized.

**Before:** build the entire v2 subsystem → bulk convert everything → see whether old callers still work.

**After:**

| ID | Kind and result | Prerequisite | Evidence required |
| --- | --- | --- | --- |
| D0 | Supporting characterization fixture for representative v1 records | Existing reader | Capture exact visible values from a disposable representative fixture; consumer D1. Not migration completion. |
| D1 | Migrate one bounded local cohort and read it through the v2 reader | D0 and agreed format semantics | Visible values match D0; v1 originals remain intact; interrupt before and after output publication, then retry without loss or duplicates. R1/R2/R3 for this cohort. |
| D2 | Expand to remaining authorized record shapes | D1's proven transition | Include empty/optional fields and boundary values; compare values, counts and identities; rerun interruption and retry checks where the transition differs. R1/R2 for remaining shapes. |
| D3 | Cutover readiness decision | D1/D2 evidence and compatibility checks | Evidence packet names reader compatibility, remaining unsupported shapes, restore procedure and irreversible boundary. Production switch/deletion stays blocked on operator approval. R3. |

**State ownership:** v1 remains authoritative before cutover. The migration writes a separate v2 artifact; it does not silently dual-write both representations. This simple design avoids changing production writers merely to test a format transition. If live updates must be supported during migration, that is a material requirement requiring a different consistency contract.

**Concurrency:** D0/D1's coupled migration writer stays single-owner. Another executor can inspect reader compatibility or prepare interruption fixtures in disjoint test paths. Separate cohorts are not automatically independent if they share publication state. **Next frontier:** D0, then D1; D3 depends on evidence, never D1 on D3's final acceptance.

## E. Eight agents, one shared writer and unavailable service access

**Agreed requirements:** add an external service operation to an existing CLI and SDK. All producer changes initially touch one registry module. Only four participants are admitted; eight were suggested. Service sandbox credentials are unavailable and no paid calls are authorized.

**Plan:** one owner defines the minimal shared operation and owns registry edits. CLI and SDK consumers can prepare disjoint code against the agreed contract. A fourth participant can prepare a shared boundary fixture/check if it has a concrete consumer. This gives at most four useful development lanes after the contract handoff, not eight independent production integrations.

**Evidence:** fixture runs prove local parsing and error presentation only. The real service criterion stays open on authorized sandbox access. Do not obtain credentials through chat, buy access, substitute another service or call fixture PASS an integrated result. Work requiring the unknown service semantics waits or is explicitly exploratory.

**Replan delta:** if the service's real error contract differs, revise the contract, retain unrelated CLI parsing evidence, invalidate affected error-mapping/SDK checks, and route the change to those owners. Preserve existing claims. If only the implementation author is free, independent acceptance remains unavailable, not reassigned to that same author under a new role.

**Next frontier:** agree the minimal contract from available evidence; perform authorized local work; name the external-access decision and owner. No production completion claim until the actual boundary passes.
