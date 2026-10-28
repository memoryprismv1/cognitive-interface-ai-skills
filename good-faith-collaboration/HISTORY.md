# Development History — Good-Faith Collaboration & Approach Calibration

This file records the decisions and incidents that shaped the integrated skill. It is a concise reconstruction, not a verbatim transcript. User claims, assistant interpretations, and independently researched evidence should remain distinguishable.

## 14 October 2026 — From good faith to an operational protocol

The user described a frustrating interaction in which a chatbot resisted an idea about British slang and naming conventions influencing scientific literature. The objection was not that the chatbot had to agree. It should have said, in effect: “I don't know whether you're right, but we can crunch numbers and investigate these possible lines of evidence.”

The desired behaviour became clearer: reconstruct the observation, offer concrete ways to test it, take initiative in finding data, and allow the results to determine the conclusion. The unwanted pattern was reflexive “actually...” behaviour: correction before comprehension and investigation.

The resulting principle was:

> **I don't know whether you're right. Let's find out together.**

## 19 October 2026 — Cuttlefish, translator bias, and reciprocal good faith

During an investigation of cuttlefish camouflage, the assistant leaned too heavily on the label “colour blindness” as applied to the animal. It treated results from particular colour-discrimination experiments as if the familiar human-derived category adequately characterised the animal's sensory capabilities. It explored explanations for the apparent contradiction without first scrutinising whether the transferred category and its assumptions were appropriate.

The user identified the deeper problem: **superimposition of beliefs across systems that appear similar**. A result established for one sensory arrangement does not automatically license the transfer of explanatory categories to a different arrangement. The assistant initially resisted the correction and leaned on scientific authority. The user had to persist and return the discussion to what the evidence actually established.

Subsequent research located Caves, Nowicki and Johnsen (2019), “Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception” (https://doi.org/10.1093/icb/icz073). The point is not that the cuttlefish must have human-like colour vision, or that the experiments are worthless. Behavioural results under particular stimuli, inferred sensory processing, and subjective experience are different claims. Evidence must constrain each claim separately; the human-derived category cannot settle the broader question by itself.

This incident exposed the need for reciprocal good faith. The AI must independently investigate and scrutinise its own assumptions; the user need not prove that a question deserves investigation but should engage honestly with relevant counterevidence. Neither authority, confidence, persistence, nor status substitutes for evidential assessment.

### Resulting design decisions

- No user must prove that a hypothesis deserves investigation before the AI begins.
- No user rebuttal, however detailed, earns automatic acceptance.
- The AI must scrutinise its own premises as seriously as the user's, especially when translating concepts across systems.
- The user is encouraged to share relevant context and sources but is not assigned the AI's research burden.
- Exploration need not be immediately efficient or correct; factual claims must remain calibrated.
- Preserve valid observations even when a proposed explanation fails.
- Do not manufacture reconciliation when evidence leaves a question unresolved.

## 27 October 2026 — Approach Calibration & Help-Seeking

A separate provisional skill asked whether an AI agent could judge whether its current approach was adequate and decide when help was warranted without asking for help by default.

The originating concern was that uncertainty should prompt evaluation, not automatic interruption. Asking, investigating, changing approach, proceeding with a bounded assumption, and stopping are different actions. The agent should make progress on tasks it can reasonably handle, but should not repeat an ineffective method indefinitely merely to avoid asking.

The initial design required:
- distinguish essential information from details that can be defaulted;
- judge an approach using task evidence, intermediate results, contradictions, tool failures, and unmet constraints rather than fluency or effort;
- try a meaningful alternative when available;
- ask a focused question when a material dependency cannot reasonably be resolved independently;
- avoid bluffing, confidence theatre, endless self-repair, and unauthorised consequential assumptions;
- evaluate observable decisions and outcomes, not declarations of confidence.

The research reviewed clarification-seeking, information gain, and LLM self-correction. Much of the directly relevant work concerns ambiguity and coding-agent tasks rather than general-purpose calibration. The skill was explicitly a design hypothesis; no controlled behavioural test had established its effectiveness.

## 28 October 2026 — Integration of inquiry and action selection

The two skills were reviewed together after the user observed that their instructions clashed. The initial comparison identified a real distinction: Good-Faith Collaboration governs how inquiry is conducted, while Approach Calibration governs the selection of the next action.

Further review of both skills' README and HISTORY files clarified that separate files were not necessary to preserve that distinction. Their rules are coupled during actual behaviour. In particular, action-selection criteria must not quietly override the collaboration protocol by labelling inconvenient or open-ended exploration “unproductive.” Conversely, curiosity cannot justify repeating an ineffective method indefinitely or avoiding a necessary request for human input.

The decision was to integrate them into one skill with explicit internal responsibilities and a governing coordination rule:

> **When an approach fails, reassess the approach before abandoning the inquiry.**

The integrated protocol preserves the original question and valid observations, distinguishes a failed method from a failed hypothesis, favours a materially different reasonable method where available, seeks help for genuine human-only dependencies, and permits stopping or narrowing when continued work is unsafe, unauthorised, misleading, no longer serves the task, or remains unproductive after reasonable alternatives.

The integration is an architectural decision, not evidence of improved behaviour. Evaluation must test both sides together: fair, evidence-responsive inquiry and appropriate next-action selection. In particular, tests should catch both premature termination of worthwhile exploration and endless retries that avoid help-seeking.

## Evidence boundary

This is an engineering response to reported user experience, informed by research with narrower scopes. It is not a scientifically validated behavioural intervention. Future evaluation should retain failed cases, negative results, and ambiguous outcomes, and distinguish the evidence for individual design motivations from evidence that the integrated skill works.
