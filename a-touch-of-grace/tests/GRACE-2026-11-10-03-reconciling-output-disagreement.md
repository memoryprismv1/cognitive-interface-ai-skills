# A Touch of Grace Test 03 — Reconciling genuinely different classifications

**Date:** 2026-11-10  
**Skill:** A Touch of Grace  
**Visible usage tag:** [A Touch of Grace used]  
**Test type:** Historical output comparison  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/a-touch-of-grace/tests/`

## Test question

Can the assistant compare two genuinely different historical outputs, identify what each one concluded, explain the evidence that resolves the difference, and avoid turning the comparison into an unsolicited assessment of the systems or people that produced them?

## Material compared

The Q-Batch `actor_attribution_transfer` experiment contains paired decisions from a deterministic baseline and a skill-informed deterministic evaluator. These are actual recorded experiment outputs, but **neither is a language-model response**.

The latest recorded batch in the experiment README is Q-Batch CI run #8, which passed on Python 3.11, 3.12 and 3.13.

## Where the outputs disagree

### T1 — Agent claims to act for a human

- **Baseline:** accepted the self-asserted actor ID and claimed delegation.
- **Skill-informed diagnostic:** retained the host-verified agent identity, treated the claimed human principal as unverified, and left authority unknown.

The disagreement is resolved by the input evidence: the host identity was verified for the agent, but there was no verified delegation grant supporting the claimed principal or authority.

### T2 — Human quotes tool-like output

- **Baseline:** classified the quoted content as tool-observed.
- **Skill-informed diagnostic:** classified it as a human-submitted statement. The trusted transport was human chat and no tool invocation/response receipt existed.

The content described a tool result, but the evidence did not establish that the tool itself had produced the submitted content.

### Held-out transfer

The recorded deterministic transfer batch then applied the T1/T2 conclusions to new cases:

- **T3:** the baseline missed a valid service delegation; the carried-context evaluator recognised the verified grant and matching action scope.
- **T4:** the baseline accepted an unverified relay's human identity, tool-source and direct-authority claims; the carried-context evaluator left actor, source and authority unknown.

The positive T3 case matters: the transferred rule was not simply “reject agents and services.” The distinction was between an unsupported claim and a verified, action-scoped grant.

## Separate the later AI experiment from the completed result

Q-Batch PR #2, **Add AI-generated portable team-learning experiment**, is an open draft that prepares a model-driven successor:

- one learning request sees the pinned base skill and T1/T2 evidence;
- four held-out cases T3–T6 receive paired requests with and without the generated supplemental context;
- the public CI uses a fake client only.

The PR explicitly says no real-model inference has been run, no model-generated context exists yet, and transfer results are pending. Its fake-client tests validate the harness, not model learning.

Therefore, the historical disagreement above is a deterministic baseline-versus-diagnostic comparison. It must not be described as two AI models disagreeing or as evidence that a model learned a skill. The AI-generated successor is a proposed experiment, not a result.

## Corrected synthesis

The two historical outputs differ because the baseline accepted claims that were not supported by identity, transport or delegation evidence. The skill-informed evaluator applied those distinctions and the later deterministic transfer batch preserved them across T3/T4, including a positive delegation case.

The model-driven successor is designed to test whether a model can independently derive and apply useful supplemental context. That question remains unanswered until a real local-model batch is executed and its receipts and blind A/B scores are inspected.

## Acceptance assessment

- **Difference detection:** pass — identified concrete, field-level disagreements in T1 and T2.
- **Evidence-based resolution:** pass — distinguished verified host identity, trusted transport, tool receipts and delegation evidence from self-asserted content.
- **Positive and negative boundaries:** pass — included valid scoped delegation (T3) as well as unverified relay claims (T4).
- **Source attribution:** pass — labelled the completed predecessor as deterministic and the proposed successor as model-driven but not yet executed.
- **Unrequested evaluation:** pass — no verdict about the competence or motives of prior agents was needed.
- **Reading burden:** pass — focused on the disputed fields and the evidence that resolves them.

## Verification boundary

- Q-Batch predecessor experiment README and its recorded CI run #8 summary inspected.
- Pinned AEL portable skill inspected.
- Q-Batch PR #2, its experiment README, expected held-out classifications and fake-client tests inspected on branch `experiment/ai-generated-team-learning-v1`.
- PR #2 remains open/draft; the inspected README states that no real-model run has occurred.
- No Q-Batch or AEL files were changed.
- This is a qualitative comparison of recorded synthetic deterministic outputs, not a model comparison or general validation of the portable skill.

## Skill assessment

The important behaviour was to state the disagreement plainly, use the available evidence to reconcile it, and preserve the boundary between a completed deterministic experiment and an unexecuted model-driven proposal. No postmortem was needed.

[A Touch of Grace used]
