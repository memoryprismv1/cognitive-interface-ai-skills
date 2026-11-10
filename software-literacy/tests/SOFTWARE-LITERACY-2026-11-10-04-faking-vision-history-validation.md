# Software Literacy Test 04 — Does Workbench validation inspect edit history?

**Date:** 2026-11-10  
**Skill:** Software Literacy  
**Visible usage tag:** [Software Literacy used]  
**Target project:** `memoryprismv1/faking-vision` (read-only inspection)  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/software-literacy/tests/`

## Test question

Does the Workbench's `fv validate` check whether the current packet agrees with its recorded edit history, as required by the current FV specification?

## Finding

**The current editor-level validator does not inspect the edit log.**

I inspected `function validate()` in `PACKETS/tools/FV_Edit_Visual_Workbench.html`. It checks:

- required packet fields and the environmental stress enum;
- duplicate or missing OI IDs;
- MSRM-to-OI references;
- current active-response references and whether the OI has a corresponding response state;
- explicit test expectations;
- current passive affected-object references;
- selected FV version mapping.

The function does not read `packet.edit_log` or inspect edit-log entries.

## Why this is a gap

The current `SPECIFICATION/FV_Working_Process_Specification.md` environmental-response section assigns the edit log specific responsibilities. It says the log must record edit events, changed properties, affected IDs, response classification, provenance, outcome, and before/after references. It also requires shared IDs to resolve and says conflicting copies of edit classifications are not allowed.

The validation section further says that active movement or shelter-seeking must be checked across OI, MSRM, the edit log, and the edited image.

The Workbench's validator can therefore report PASS for a packet whose *current* OI, ENVIRONMENT and MSRM references pass its checks, while a malformed or contradictory edit-log entry goes unnoticed. This is a validation coverage gap; it does not prove that every existing packet contains a bad history entry.

## Demonstrated inspection result

I checked the complete source body of `validate()` between its declaration and `exportBundle()`:

- Function body length inspected: 3,652 characters.
- References to `edit_log` / `editLog`: none.
- Edit-history consistency checks: none.

The validator does read current OI and ENVIRONMENT response fields. That is not equivalent to checking the historical before/after records in `edit_log.json`.

## Recommended test cases

Add validator tests using packets whose current state is otherwise valid:

1. A history entry references an object ID absent from OI.
2. A history entry claims a property change whose recorded `after` value conflicts with the current OI or MSRM state, where the schema expects that event to describe the current result.
3. An active-response classification in the log conflicts with the event's before/after behaviour or location data.
4. A passive/active classification is duplicated inconsistently between the event record and the corresponding state record.
5. A valid sequence of multiple edits is accepted, so the validator does not incorrectly require every historical `after` value to equal the *current* state. Later edits may legitimately supersede earlier ones.

The fifth case matters: history is a sequence, not a second copy of the current packet. A correct audit must replay or reconcile the sequence, not compare every old event directly with today's state.

## Proportionate correction

Treat this as a separate **history consistency audit** rather than adding a simplistic equality check to the existing schema validator.

A useful implementation would:
- validate each log entry's shape and required fields;
- check that referenced IDs resolve, subject to schema-approved exceptions;
- check each event's before/after transition against the preceding state in the sequence;
- confirm the final replayed state agrees with current OI, ENVIRONMENT and MSRM;
- distinguish malformed history (FAIL) from incomplete provenance or unsupported claims (WARN / unresolved);
- keep JSON parsing, structural validation, semantic validation, and visual audit as separate reported outcomes.

This is a recommendation, not an implementation. A robust replay audit needs the precise event schema and legacy compatibility rules.

## Verification boundary

- **Source inspection:** completed against current `main`.
- **Specification comparison:** completed.
- **Existing browser tests:** reviewed; they cover edit-log append/preservation in selected flows, but not reconciliation of the full history against current packet state.
- **Runtime reproduction / browser suite:** not run for this test.
- **Faking Vision files changed:** none.
- **Cognitive skill test record:** this file only.

## Software Literacy assessment

The key distinction is between checking the current data and auditing how that data came to be. A packet can be structurally plausible now while its recorded sequence of changes is incomplete or contradictory. The report separates that demonstrated coverage gap from the unproven claim that existing packets are corrupted, and avoids proposing a naive history comparison that would reject legitimate later edits.

[Software Literacy used]
