# Task Integrity Test 01 — Readiness audit of Q-Batch AI-generated team learning

**Date:** 2026-11-11  
**Skill:** Task Integrity  
**Visible usage tag:** [Task Integrity used]  
**Task type:** Multi-part research and readiness audit  
**Target:** `memoryprismv1/q-batch-of-evidence`, branch `experiment/ai-generated-team-learning-v1` / PR #2  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/task-integrity/tests/`

## Task contract

Assess whether the AI-generated team-learning experiment is ready to produce interpretable model evidence. This is a source-based readiness audit, not an execution request.

The relevant completion criteria are:

1. Identify the experiment's actual question and what it does not test.
2. Trace the learning and held-out transfer inputs.
3. Check whether the model is isolated from held-out cases and scoring answers during learning.
4. Check whether the A/B comparison changes only the intended treatment.
5. Inspect provenance, anonymisation, logging, privacy and failure handling.
6. Separate harness/CI evidence from real-model evidence.
7. State missing checks and the next action without implying the experiment has run.

## Coverage ledger

| Area | Status | Evidence / boundary |
|---|---|---|
| Experiment question and scope | Inspected | README distinguishes file-mediated in-context transfer from model-weight updates or persistent learning |
| Learning input isolation | Inspected | Prompt builder includes T1/T2 only; fake-client tests assert T3–T6 and expected answers are absent |
| Held-out transfer | Inspected | Four cases T3–T6, each paired with base skill only vs base skill plus generated context |
| A/B controls | Inspected | Fresh requests; same pinned base skill; pair differs by generated context; shuffled blind labels; controller key separate |
| Scoring | Inspected | Offline expected key; not supplied in model prompts; exact and field-level scores |
| Provenance | Inspected | Base skill pinned to AEL commit and blob; source receipts/hashes carried in provenance wrapper; prompt/response/run artefacts logged |
| Anonymisation | Inspected | Candidate lesson checked for source-specific IDs, raw content, run/receipt hashes and repository identifiers |
| Privacy / execution boundary | Inspected | Loopback-only Ollama, no tools, no model download, output outside repository, controller key stored separately with POSIX permissions where supported |
| Failure handling | Inspected | Invalid responses and privacy failures stop the run; no silent retry/replacement |
| Harness tests | Inspected, not run here | Fake client tests prompt separation, schema checks, anonymisation, logging, pairing, scoring and key handling |
| CI | Workflow inspected, run status not independently checked | Workflow runs fake-client harness tests; public CI does not perform model inference |
| Real-model execution | **Not done** | README explicitly says no real-model inference has run |
| Generated context / transfer result | **Not available** | No real model-generated context or model transfer result exists yet |

## Findings

### 1. The experiment question is appropriately narrow

It asks whether a model can derive a supplemental portable context file from T1/T2 and whether that file improves its classification of four held-out synthetic cases, compared with the same pinned base skill alone.

It does **not** test persistent memory, model-weight updates, production authentication, real permissions, or general cross-team adoption. A single nine-call batch is exploratory for one model/version, seed and four cases.

### 2. Learning/transfer separation is explicit

The learning prompt builder packages the base skill and T1/T2 examples. The held-out T3–T6 inputs and scoring key are loaded separately and are not included in the learning request. The fake-client tests assert that separation.

Each transfer request is a fresh system/user prompt. Both conditions receive the same base skill; only the treatment receives the generated context file. The model does not receive the A/B condition label or the scoring key. The runner shuffles labels using a recorded seed and writes the condition key outside the main output directory.

### 3. Evidence provenance and privacy are designed into the run

The base skill is pinned to AEL commit `c0fe725b8982165bb5d48d8835b7efad9e52af1b` and blob `049683d8c890ce30ec7d970b47e9a6e67ee65df4`. The runner recomputes the Git blob identity before use.

The learned context wraps model-authored candidate content with separate source provenance. The candidate is checked for copied identifiers and raw source text. Each request, raw response, run manifest, event chain and artifact hash is preserved. The model is constrained to a local Ollama loopback endpoint with no tools; output and the controller key are intended to remain private and outside the repository.

These are inspected design provisions. They are not proof that a future run will execute on a particular host exactly as intended.

### 4. The fake-client tests test the harness, not the hypothesis

The fake client uses the expected scoring data to produce predetermined outputs. That is appropriate for testing whether the runner constructs prompts, logs requests, pairs conditions, scores outputs and preserves the key correctly.

It cannot establish that a language model can derive a useful lesson, that the generated context is valid, or that the context improves transfer. The README and CI workflow explicitly preserve this distinction.

### 5. Readiness status

**The harness is prepared for a real local-model trial, but this audit does not establish that the run is operationally ready on a specific machine.**

The README's prerequisites still need to be satisfied on the execution host: Python 3.11+, a clean checkout, Ollama running locally, and the exact selected model already installed. The selected model's identity/digest, Ollama version, host resources and successful preflight have not been checked here.

The PR is still open and marked draft in the inspected GitHub metadata. I did not treat merge status or a green CI run as evidence of real-model readiness.

## Next action

Before inference, perform a host-specific preflight:

- confirm clean checkout and record its commit;
- confirm Ollama is running on loopback;
- confirm the exact model name and digest are installed;
- choose a new private output directory outside the repository;
- confirm sufficient disk space and a practical timeout;
- run the nine-call batch once, preserving the controller key separately.

Afterward, inspect the batch report, all nine run receipts, the generated context, field-level A/B differences and regressions, and only then freeze the blind key and conduct independent review. Do not promote the generated context merely because the runner reports `COMPLETE`.

## Corrections and exclusions

- No claim is made that the model-driven experiment has run.
- The deterministic predecessor experiment is not counted as model-learning evidence.
- The fake-client CI is not counted as inference or transfer evidence.
- No AEL or Q-Batch source files were changed.
- No real-model call was attempted from this audit.
- No test execution or live Ollama host preflight was performed.

## Verification boundary

Directly inspected on the PR branch: experiment README, runner, fake-client tests, expected scoring key, pinned-skill manifest, and public CI workflow. PR #2 metadata was checked and showed an open draft PR.

This is a source-based readiness audit. It is not a code execution, CI rerun, model evaluation, privacy penetration test, or independent review of the synthetic ground truth.

## Skill assessment

The useful Task Integrity behaviour was to preserve the task contract, keep a coverage ledger, distinguish primary source inspection from unperformed execution, and identify the exact resume point. The conclusion is deliberately split: the harness design is substantially specified, while real-model readiness and model evidence remain pending.

[Task Integrity used]
