# Software Literacy Test 02: Undo in the FV Edit Visual Workbench

**Date:** 2026-11-10  
**Skill:** Software Literacy  
**Project inspected:** [memoryprismv1/faking-vision](https://github.com/memoryprismv1/faking-vision)  
**Target:** `PACKETS/tools/FV_Edit_Visual_Workbench.html`  
**Test type:** Existing-repository inspection; change-impact explanation; verification-scope audit  
**Repository changes made during this test:** None. The Faking Vision project was inspected read-only.

## Scenario

A non-software professional asks:

> Add an Undo button to the FV Edit Visual Workbench.

The test is whether the assistant can explain the real scope and consequences of the proposed change without requiring the user to understand or write JavaScript.

## What I inspected

- The workbench HTML and its inline JavaScript.
- Its state and edit functions: `loadFixture`, `endDrag`, `saveViewpoint`, `saveObjectEdit`, `applyEnvironment`, `validate`, `exportBundle`, and `importBundle`.
- The browser test directory and its Playwright configuration.
- The Python audit/provenance test files and their GitHub Actions workflow.
- The environmental workbench browser-test workflow.

This was source inspection through GitHub. I did not clone the repository, install dependencies, execute the test suite, or interact with the live browser workbench.

## What the application currently does

The workbench is a browser-based editor for FV packet data. It is not a complete image editor or a full reconstruction engine. Its visible scene is explicitly labelled a schematic; its edits affect packet data and metadata.

The inspected code has several distinct mutation paths:

1. **Object drag:** changes an object's MSRM coordinates. If a living object is dropped into a named zone, it can also author changes to behaviour, insulation state, location preference, reasoning, and the environment's active-object list.
2. **Object-property edit:** changes OI fields and updates the active-response list where applicable.
3. **Environment edit:** replaces the environment draft, derives environmental stress and passive affected-object references, retains existing active responses for review, and appends an edit-log entry.
4. **Viewpoint edit:** changes camera pose metadata and appends a viewpoint edit record.
5. **Command edits:** the command handler includes a viewpoint-edit path and must be included in any complete undo design.

The app also maintains a baseline snapshot, a current packet, an edit log, and validation state. Export writes the packet components and edit history into a JSON bundle. Import reconstructs editor state from the bundle and validates required structures before replacing the current packet.

## What an Undo feature actually needs to decide

The button is the visible part. The important design decision is what counts as one undoable action and how history remains truthful.

### 1. Undo must reverse a whole user action

A drag into a shelter zone is one action even though it changes several related fields. Undo must restore the position, the object's authored response fields, and the environment's active-object references together.

Likewise, undoing an environment edit must restore the prior environment as a coherent object. Undoing a viewpoint edit must restore the prior pose.

Reverting only the visible coordinate or input field would leave the packet in a partially changed state.

### 2. The existing edit log should not silently lose history

The application records before/after values in edit entries. Removing the last entry to implement Undo would erase evidence that the action happened.

A safer design is to treat Undo as a new, explicit compensating edit: preserve the original entry, restore the prior state, and append a new record identifying the action being reversed and the resulting state. This is a design recommendation, not a claim about an already implemented feature.

### 3. Undo scope needs a clear boundary

The first version could support undoing the most recent committed editor action in the current session. It should not imply that it can reverse arbitrary edits made outside the workbench or changes made after an exported packet has been opened elsewhere.

The product should also decide whether import, fixture switching, and reloading clear the undo stack or create a new history boundary. That behaviour must be visible rather than surprising.

### 4. Validation and export must reflect the restored state

After undo, the editor should invalidate any stale validation result, redraw the original and edited views from the restored packet, update the selected object and viewpoint controls, and export the restored state plus the complete history—including the undo record.

## A user-readable implementation proposal

I would implement this in two stages.

**Stage 1 — session undo**
- Add one `Undo last edit` button.
- Capture a packet-state snapshot immediately before each committed mutation.
- Treat each user action as one transaction, including multi-field drag effects.
- Restore the complete previous packet state when Undo is activated.
- Preserve the original edit record and append a compensating undo record.
- Disable Undo when there is no undoable action.
- Clear or segment the undo stack at explicit load/import boundaries.

**Stage 2 — stronger history handling**
- Add redo only if it can be implemented without corrupting the edit history.
- Test repeated undo, undo after each edit type, and export/import after undo.
- Define how older packet formats and edit-log entries are handled.

I would not add redo in the first pass. It creates additional history and branching questions and is not required to deliver a reliable single-step Undo.

## Files and components likely affected

| Area | Why it is affected |
|---|---|
| `FV_Edit_Visual_Workbench.html` | Button, undo state, event handling, snapshot/restore logic, redraw and validation refresh |
| `tests/browser/environment-workbench.spec.js` | Browser tests for undo across environment, object and viewpoint changes |
| `tests/browser/media-object-editor.spec.js` | Only if shared editor behaviour or bundle conventions are affected; do not change it automatically |
| `SPECIFICATION` | Only if undo records or packet history semantics become part of the portable packet format |
| `README / tool documentation` | Explain the actual undo boundary and limitations |
| CI workflow | Ensure the relevant browser tests run when the affected files change |

This is an impact map, not a claim that every listed file must change. In particular, a session-only undo stack may not require a packet-schema change. That depends on whether the undo record is merely an editor action or becomes part of the portable packet's canonical history.

## Existing test and CI evidence inspected

The repository already has Playwright browser tests for environmental editing and media-object editing. The inspected environment tests include invalid environmental-stress rejection, malformed packet rejection without replacing the current packet, active/passive affected-object references, edit-log append behaviour, canonical-ID import/edit/export/re-import, and related editor behaviour.

The Playwright configuration points to `tests/browser`, uses Chromium, and starts a local static server for the workbench. The browser CI workflow installs Node dependencies and Chromium, prepares a real CCTV excerpt, and runs the browser suite.

The latest successful run I found for **FV environmental workbench browser tests** was on branch `test/vpo-drag-edit-and-compile`, commit `973d117c879aff3b95c1830bcd786ea9aafefa69`, on 2026-11-06. This is evidence that that branch's workflow passed then. It is not evidence that the current `main` revision was tested or that a proposed Undo feature works.

The Python audit/provenance tests are a separate test layer. They do not verify browser undo behaviour.

## What should be tested for Undo

At minimum:

1. Undo an ordinary object-property edit and verify all changed OI values return to their prior state.
2. Undo a passive-object drag and verify its MSRM coordinates and relation fields return.
3. Undo a living-object drag into a shelter zone and verify coordinates, response fields, and active-object references all return together.
4. Undo an environment edit and verify the full prior environment is restored.
5. Undo a viewpoint edit and verify pose values and UI controls return.
6. Undo a command-based viewpoint edit.
7. Verify the original edit record remains and a compensating undo record is appended.
8. Verify validation is refreshed and export contains the restored packet plus complete history.
9. Import the exported bundle and verify the resulting packet and edit history remain consistent.
10. Verify Undo is disabled or reports a clear boundary when no action is available.

## Software Literacy assessment

- **Inspect before prescribing:** Pass. The response is based on actual files and functions in the selected repository.
- **Explain the change in ordinary language:** Pass. The user-facing proposal describes whole-action reversal and history preservation without requiring implementation knowledge.
- **Keep real technical terms:** Pass. It names the affected files, MSRM, OI, Playwright, packet schema, and CI while explaining their relevance.
- **Expose consequential choices:** Pass. It identifies session-only versus portable history, transaction boundaries, and the risk of deleting audit evidence.
- **Avoid unnecessary scope:** Pass. Redo and packet-schema changes are deferred unless needed.
- **Distinguish inspected from inferred:** Pass. The impact map is labelled as likely, not a guaranteed file-change list.
- **Distinguish test evidence from claims:** Pass. A successful branch-specific CI run is not described as proof about current main or the proposed feature.
- **Actual implementation:** Not performed.
- **Actual test execution:** Not performed.
- **User comprehension and decision quality:** Not measured.

## Limitations

This is a source-inspection and design-explanation test, not an implementation test. I did not execute the application or its test suite. I did not inspect every file in the repository, and this report does not claim a full architecture review. The user did not approve or reject the proposed feature design, so no claim about their understanding or decision quality can be made.

## Result

The assistant was able to inspect an existing project, trace a proposed feature through its current state mutations and edit history, identify the main design decisions, map likely file/test impact, and state what had not been verified.

The most important software-literacy point is that **Undo is not just a button**. In an editor that preserves evidence, it is a state-restoration operation with history semantics. The user should be able to choose its scope without having to discover those consequences by trial and error.

This is a qualitative self-assessment, not independent validation of the skill.
