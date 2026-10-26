# Task Integrity

**Zenodo record:** [Archived release](https://zenodo.org/records/23666595)

**Skill:** task-integrity

**Purpose:** Keep AI work aligned with the requested scope, make evidence and coverage visible, and ensure that completion claims match the work actually performed.

## Why this is a general capability

A chatbot can produce a fluent, plausible response while silently omitting requested parts, mixing directly inspected evidence with summaries or memory, or presenting a partial result as complete. The same underlying failure can appear in research, literature discussion, code review, archive analysis, data work, document production, and long-running projects.

The answer is not a separate skill for each type of disappointment. It is a reusable capability for tracking scope, coverage, provenance, status, and corrections across tasks.

## Design principle

> **The user should not have to reconstruct what was done, what was omitted, or what the result actually rests on.**

## Core mechanism

For substantial tasks, preserve a compact task ledger with the intended scope, completion criteria, actual coverage, pending work, excluded branches, evidence sources, verification status, and next action. The ledger is updated as work proceeds and carried into handoffs.

This ledger is not an invitation to produce verbose status reports in every response. It is working infrastructure. Surface only the information needed for the user to understand the state and make decisions.

## Cognitive-interface rationale

A conversation is an interface through which the user observes and directs work. If the interface hides omissions or blurs the difference between inspected evidence and remembered information, the user cannot accurately calibrate conclusions or know what to do next. An explicit task state makes coverage and uncertainty inspectable instead of requiring the user to infer them from confident language.

This is an engineering rationale. It should not be presented as an experimentally established effect of this exact skill.

## Example as a test case

In one literature discussion, a chatbot supplied selected passages and summaries, mixed them with unverified remembered details, and allowed the discussion to proceed as if the evidence were more complete than it was. The user had not read the full work and was responding to the material the chatbot had chosen to supply.

That incident illustrates the general issue: selection, provenance, and coverage were not made visible. The skill therefore applies well beyond literature. The same checks matter whenever a user relies on a chatbot's selection or synthesis of material.

The incident is a test case for the capability, not the definition or scope of the skill.

## Skill-library design rule

Record incidents accurately and separately in the appropriate history. Extract the general mechanism they reveal. Extend an existing skill when the capability is already covered; add a new skill only when it contributes a distinct, reusable capability. Avoid turning the skill library into an inventory of provider-specific complaints.

## Evaluation

Test the skill using different task types, including research, coding, file analysis, and long multi-part conversations. Measure:
- whether requested components are accounted for;
- whether the status matches the work completed;
- whether evidence provenance remains visible;
- whether gaps survive handoffs;
- whether corrections identify exactly what changed;
- whether lessons generalise appropriately without misattribution.

## Evidence status and limits

This is a proposed operational protocol, informed by observed interaction failures. Its effectiveness should be established through tests. It does not guarantee factual correctness or remove the need for domain-specific expertise.
