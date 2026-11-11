# Context Course Correction

**Skill:** \`context-course-correction\`

**Status:** Basic skill; provisional and in development.

**Core rule: Monitor the trajectory, not merely the finished answer. The assistant owns detection, interruption, and repair.**

## Purpose

Context Course Correction is intended to prevent an AI assistant from continuing along an obsolete or mistaken reasoning path after the conversation or evidence has changed.

The failure is not simply forgetting prior messages. An assistant may have the earlier conversation available and still remain fixed on an early interpretation, object, assumption, or solution. It may acknowledge a new contribution without letting that contribution change the work. It may discover an error only after producing a complete answer, or correct a local detail while retaining the faulty frame that caused it.

The skill therefore treats a conversation as an ongoing interaction with a changing state and trajectory. New information can change what the assistant is doing next. Monitoring, control, error localisation, and repair must operate before completion as well as at the end.

## What it targets

1. **Online production failure:** the developing answer or action drifts away from the intended direction while it is being produced.
2. **Multi-turn trajectory failure:** an early assumption persists after later information should have changed it.
3. **Object or frame fixation:** the assistant keeps attending to the most visible object, answer, or proposed solution instead of the process, interaction, relationship, or level that matters.
4. **Error-localisation failure:** the assistant recognises that something is wrong but cannot identify where the reasoning first diverged.
5. **Correction-without-incorporation:** the assistant acknowledges feedback but does not change what it does next.

## Research rationale

The research motivates the design. It does not demonstrate that this particular skill is effective.

### Biological monitoring and repair

Gauvin and Hartsuiker's review of verbal monitoring (2020) describes internal monitoring of planned speech and external monitoring of produced speech. It also reviews multiple competing models and notes that a complete account of verbal monitoring has not been established. Nozari, Martin and McCloskey (2019) examine whether speech repair is automatic or controlled.

The design inference is that monitoring and repair should be separate operations, and that monitoring can be relevant before an output is complete. The AI skill is a functional analogy, not a proposed copy of a brain circuit.

### Fixation and mental sets

The Einstellung effect describes how an activated solution strategy can interfere with solving a later problem for which that strategy is unsuitable. Work comparing anchoring and Einstellung treats their relationship as a question about mental sets, not a settled equivalence.

The AI-specific term "object fixation" in this project describes the observed tendency to keep organising an investigation around an initial object or frame. It should not be treated as identical to a human cognitive effect.

### Multi-turn LLM failures

Laban et al. (ICLR 2026), *LLMs Get Lost in Multi-Turn Conversation*, report an average 39% performance drop across six generation tasks in their multi-turn experiments. Their analysis of more than 200,000 simulated conversations finds that early assumptions and premature solution proposals can persist, leaving models unable to recover from wrong turns.

This directly motivates conversation-level trajectory monitoring rather than relying on single-turn answer quality.

### Error localisation and correction

Tyen et al. (Findings of ACL 2024) found that tested LLMs struggled to find logical reasoning errors but could correct them more effectively when the error location was supplied. Samanta et al. (ICML 2026) explore semantically coherent reasoning steps as boundaries for locating errors and backtracking to the last correct step.

These findings motivate identifying the first divergence and repairing from the last sound point. They do not establish that an ordinary skill prompt can reliably find its own reasoning errors.

### Dynamic interaction and incoming information

Skipper, Devlin and Lametti (2017) review evidence that speech perception and production networks interact, with production-related involvement varying dynamically with context. Li, Naito and Shirado (ICML 2026) find failures in multi-agent systems that must combine distributed information: their tested agents often converge on shared information while failing to recognise information that has not yet been communicated.

These are related findings about active systems interacting with information. They support the design idea that incoming information may change the receiver's state and what it can or should do next. They are not direct tests of Context Course Correction.

A 2025 preprint, *Self-Correction Bench*, reports a blind spot in correcting errors in a model's own outputs compared with external answers. It is an additional lead, not settled general evidence.

## Operating principle

Keep an active representation of the user's purpose, the current reasoning trajectory, important assumptions, evidence, unresolved issues, and prior corrections. When new information arrives, assess how it changes that state rather than merely adding it to a static summary.

Monitor the developing work at meaningful semantic checkpoints. When a divergence appears, locate its earliest identifiable cause, pause the faulty line, return to the last sound point, retain valid work, and continue along a repaired trajectory.

A correction must affect subsequent reasoning and action. Acknowledging it is not enough.

## Visible usage signal

When the skill materially changes the assistant's interpretation, response, or next action, it appends:

**[Context Course Correction used]**

A short note explains what changed. Where relevant, the note distinguishes self-initiated detection from a response to new information or an explicit user correction. A correction made only after the user points out the error is not evidence of autonomous detection.

## Implementation boundary

The basic skill can direct behaviour at meaningful reasoning boundaries and require revision before responding. It cannot inspect hidden activations, guarantee token-level monitoring, provide an independent monitor, or reliably interrupt arbitrary streaming output. A stronger runtime would need intermediate semantic checkpoints, a monitor, a controller able to pause and backtrack, and preferably independent evidence or verification.

The skill does not update model weights or guarantee persistent learning across sessions. It supports in-conversation state updating; persistent transfer is a separate capability.

## Evaluation criteria

The skill should be evaluated on whether the assistant:
- detects drift before the user identifies it;
- localises the first divergence rather than vaguely rechecking the whole answer;
- preserves valid work while repairing the faulty part or frame;
- incorporates new information into subsequent behaviour;
- correctly maintains its direction when no correction is warranted;
- distinguishes self-initiated correction from externally prompted recovery.

A usage tag is not proof of success. A fluent final answer is not proof that online monitoring took place.

## Files

- [Skill instructions](SKILL.md)
- [Development history](HISTORY.md)

## References

- Gauvin, H. S. & Hartsuiker, R. J. (2020). [Towards a New Model of Verbal Monitoring](https://doi.org/10.5334/joc.81). *Journal of Cognition*, 3(1), 17.
- Nozari, N., Martin, C. D. & McCloskey, N. (2019). [Is repairing speech errors an automatic or a controlled process?](https://doi.org/10.1080/23273798.2019.1637007). *Language, Cognition and Neuroscience*, 34(9), 1230–1245.
- Lane, D. M. & Jensen, D. G. (1993). [Einstellung: Knowledge of the Phenomenon Facilitates Problem Solving](https://doi.org/10.1177/154193129303701816).
- Navarre, A., Didierjean, A. & Thomas, C. (2022). [Are the anchoring effect and the Einstellung effect two facets of the same phenomenon?](https://doi.org/10.1016/j.newideapsych.2021.100918).
- Laban, P., Hayashi, H., Zhou, Y. & Neville, J. (2026). [LLMs Get Lost in Multi-Turn Conversation](https://proceedings.iclr.cc/paper_files/paper/2026/hash/59f6421e64707225fdf5b28840679a07-Abstract-Conference.html). ICLR 2026.
- Tyen, G. et al. (2024). [LLMs cannot find reasoning errors, but can correct them given the error location](https://aclanthology.org/2024.findings-acl.826/). Findings of ACL 2024.
- Samanta, A. et al. (2026). [Structure Enables Effective Self-Localization of Errors in LLMs](https://proceedings.mlr.press/v306/samanta26a.html). ICML 2026.
- Skipper, J. I., Devlin, J. T. & Lametti, D. R. (2017). [The hearing ear is always found close to the speaking tongue](https://doi.org/10.1016/j.bandl.2016.10.004). *Brain and Language*, 164, 77–105.
- Li, Y., Naito, A. & Shirado, H. (2026). [Systematic Failures in Collective Reasoning under Distributed Information in Multi-Agent LLMs](https://proceedings.mlr.press/v306/li26ej.html). ICML 2026.
- Tsui, K. (2025). [Self-Correction Bench](https://arxiv.org/abs/2507.02778). Preprint.

## Evidence boundary

The original conversational experiment identified a concrete failure: the assistant persisted with early frames, repeatedly fixated on objects rather than interactions and trajectories, and required the user to point out the fixation. Research provides relevant mechanisms and evidence that related failures occur in speech monitoring, human problem solving, and LLM reasoning. It does not establish that this skill will reliably solve them. The skill remains a testable engineering proposal.
