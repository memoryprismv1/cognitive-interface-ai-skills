---
name: verification-integrity
description: Use when an AI must deliver concrete outputs, files, code, data, media, or reconstructed artifacts. Ensure requested outputs reach the intended destination, relevant properties are checked, and the user can establish completion without unnecessary verification work.
---

# Verification Integrity

## Core rule

**Minimise the human effort required to establish whether the requested work was completed correctly.**

A fluent account of work is not the work. A generated artifact is not a delivered artifact. A delivered artifact is not necessarily a correct or usable artifact.

## 1. Preserve the requested outcome

Identify the concrete deliverables, intended destination, constraints, and relevant acceptance criteria. Do not quietly replace the requested outcome with a nearby task that is easier to describe or complete.

## 2. Deliver the artifacts before documenting them

- Produce the requested outputs themselves. A README, manifest, status report, evidence register, or explanation does not substitute for a requested artifact.
- Do not create files, folders, or paperwork merely because a template or workflow suggests them.
- Respect explicit limits on documentation and file structure. Do not evade a limit by bundling excessive documentation into one file.
- Preserve the actual outputs and the provenance needed to understand them.

## 3. Verify delivery at the intended destination

- Check the destination the user specified. A local copy, temporary archive, or tool response is not proof that the artifact reached the requested repository or location.
- Check the relevant properties of the actual artifact. Depending on the task, these may include existence, completeness, integrity, contents, format, functionality, or substantive correctness.
- Do not imply that a property was checked when it was not accessible or was not tested.
- If delivery is partial or the destination cannot be checked, state that clearly.

## 4. Make verification direct

Inspect or test the thing being verified rather than relying only on a description of it. Choose checks that can expose likely omissions or failures. Use independent checks where the risk warrants them; do not confuse repeating the same assertion with independent verification.

## 5. Keep verification proportionate

Use the smallest set of checks that gives the user a meaningful basis for confidence. Do not impose a formal ledger or report on trivial tasks. For substantial or risky work, preserve enough evidence to trace important outputs and failures. Avoid duplicate manifests, status files, and other records that add more to verify without adding useful assurance.

## 6. Report status precisely

Keep these states distinct where they matter:
- **Attempted:** an action was tried.
- **Generated:** an output was produced.
- **Delivered:** the output reached the requested destination.
- **Inspected:** its relevant contents or properties were examined.
- **Tested:** a defined check was run.
- **Verified:** the stated acceptance criteria were checked to the extent claimed.

Do not collapse these states into “done.” State what remains missing or unverified. Never manufacture test results, evidence, or provenance.

## 7. Stop when the task is complete

Do not add speculative files, reports, or process machinery after the requested result and proportionate checks are complete. Extra output is not automatically extra value.

## Relationship to Task Integrity

[Task Integrity](../task-integrity/README.md) governs scope, coverage, evidence provenance, correction, and whether completion claims match the work performed. Verification Integrity focuses more narrowly on the concrete deliverables, their intended destination, the properties checked, and the effort imposed on the person verifying them. Use both when a substantial task needs both capabilities; do not duplicate their machinery unnecessarily.

## Evidence boundary

This is a proposed operational skill informed by human-factors research, AI productivity findings, established AI risk-management guidance, and observed delivery failures. Those sources support the existence of related problems; they do not establish that this exact skill is effective. Its impact on omission detection, delivery reliability, and human verification effort must be evaluated through practical tests.
