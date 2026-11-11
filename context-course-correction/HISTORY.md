# History: Context Course Correction

This history records the development of the skill from the original conversational experiment, subsequent implementation attempts, a first live sequencing check, and the research used to revise the design. It is not a verbatim transcript or proof of general capability.

## 8 November 2026 — Original experiment: online monitoring and correction

The user invited the assistant to identify something AI does badly, investigate a biological equivalent, and develop a capability. The assistant initially proposed a hippocampus–neocortex learning architecture. The user rejected that framing and introduced speech as a quality-assured output: a speaker can interrupt and correct an utterance when it does not match an internal vocal pattern.

The investigation examined speech-error monitoring, internal and external feedback, rapid self-repair, and automaticity. It distinguished:
- detecting an anticipated error before output;
- detecting a mismatch during or after output;
- deciding whether and how to intervene;
- successfully repairing the error.

The reading example introduced another distinction: a familiar word may be retrieved as a whole pattern, while an unfamiliar word may be assembled from parts. A teacher can provide a corrected complete pattern before the learner has successfully used it. For this project, the important implication was that corrective information can alter the active representation before later use. The biological account of storage was treated as a working hypothesis, not an established neural fact.

The user clarified that the model was about logic, reasoning and current AI research, not a pronunciation feature.

## 8 November 2026 — From individual correction to incoming information changing a system

The investigation widened to learning from others and combining information. It considered discovery costs, positive and negative knowledge, reliability of inherited information, and the need to revisit information when conditions change. The assistant then fixated on the thing being transferred—answers, discoveries, procedures, failures—rather than on what transmission does to a receiving system.

The user introduced vocalisation as information entering an environment and causing responses that can continue as a cascade. The relay-race analogy sharpened the point: the receiving runner is already moving, and the way the baton is handed over changes the receiver's state, trajectory and subsequent possibilities. The handoff is an interaction between moving systems, not a neutral transfer into an empty container.

The resulting working idea was that information entering a medium changes the course of events from then onwards. The original signal need not be corrupted for its effects and consequences to change. The receiver's existing state matters, and later interactions can continue to redirect the trajectory.

## Observed failure pattern

Across the experiment, the assistant:
- committed early to a hippocampus–neocortex architecture before establishing the actual problem;
- repeatedly turned observations into proposed AI features or architectures too early;
- kept organising the investigation around transferable objects instead of interactions and changing trajectories;
- shifted its frame after user contributions but did not independently identify the object fixation before the user named it;
- sometimes acknowledged the user's information without fully allowing it to change what it investigated next.

The user described the missing capability as a feedback loop: the assistant should feed conversation context back into its current direction, compare the two, and change course when required.

A subsequent attempt to teach the user prompt commands for managing fixation transferred the correction burden to the user. The user rejected that responsibility shift. The assistant must own context monitoring, detection, and repair.

## 11 November 2026 — First implementation and its omission

The first repository implementation described context tracking and trajectory review, but it was too narrow. It did not adequately incorporate the research on speech monitoring, error localisation, correction, cognitive fixation, and the way incoming information changes an active system. It also described checking before a substantial response more clearly than monitoring and interrupting while work is developing.

The user identified the missing research foundation and required the original conversations to be read again. The revised design now treats the source conversations as the primary development record and the external research as supporting evidence, not as a replacement for the observations and concepts developed in the experiment.

## 11 November 2026 — Sequencing check before the rewrite

The assistant proposed to rewrite the skill first and test it afterwards. The user reversed the order and asked for the test stage to happen first.

The assistant suspended repository changes and used the current interaction as a live sequencing check.

**Observed result:**
- The assistant changed its planned next action to follow the user's revised order.
- This was a signal-responsive correction.
- The correction was explicitly requested by the user. The assistant had not independently noticed that its previous plan should be tested before being encoded.
- Therefore, this run does **not** demonstrate autonomous detection of drift.

The original exported conversations provide a retrospective baseline: the assistant repeatedly changed direction after user contributions, but did not independently name its own object fixation before the user did. A retrospective replay is not counted as an autonomous live correction.

This is an initial qualitative observation, not a controlled test or validation.

## Research used to revise the design

### Speech monitoring and repair

Gauvin and Hartsuiker (2020), *Towards a New Model of Verbal Monitoring*, reviews internal and external speech monitoring and multiple competing accounts. It explicitly does not offer a single settled account of all verbal monitoring.

Nozari, Martin and McCloskey (2019), *Is repairing speech errors an automatic or a controlled process?*, examines the relationship between error probability and repair. The work supports keeping monitoring and the control/repair process conceptually distinct.

### Cognitive fixation

The Einstellung effect describes how a familiar or activated solution strategy can interfere with solving a later problem that needs a different approach. Navarre, Didierjean and Thomas (2022) discuss possible relationships between anchoring and Einstellung; the proposed shared basis is not treated as settled.

These sources help contextualise fixation, but the project's term "object fixation" remains an operational description of the AI interaction pattern, not a claim that it is identical to a human cognitive effect.

### LLM multi-turn drift and error localisation

Laban et al. (ICLR 2026), *LLMs Get Lost in Multi-Turn Conversation*, report substantial performance degradation in multi-turn settings and describe persistence of early assumptions and premature solution attempts.

Tyen et al. (Findings of ACL 2024), *LLMs cannot find reasoning errors, but can correct them given the error location*, distinguish mistake detection from correction when the error location is supplied.

Samanta et al. (ICML 2026), *Structure Enables Effective Self-Localization of Errors in LLMs*, investigate semantically structured reasoning steps, error localisation, and backtracking from the last correct step.

These sources motivate a repair strategy that identifies the earliest divergence instead of merely asking the model to check the finished answer.

### Dynamic interaction and collective information

Skipper, Devlin and Lametti (2017) review the dynamic relationship between speech perception and production.

Li, Naito and Shirado (ICML 2026) report failures in collective reasoning when relevant information is distributed across agents and not all of it has been expressed.

These are adjacent lines of evidence. They support considering the interaction between incoming information and an already-active receiver, but they are not direct evaluations of this skill.

Tsui's 2025 *Self-Correction Bench* is an additional preprint lead on the difference between correcting a model's own answer and an external answer. It is retained with its preprint status and limited tested model set.

## Current design decisions

- The skill monitors an evolving reasoning and action trajectory, not merely the final answer.
- It incorporates new information as a possible change to the active state, rather than just adding it to a static summary.
- It uses meaningful semantic checkpoints; it does not claim token-level introspection.
- It separates monitoring, control, error localisation, and repair.
- It seeks the earliest identifiable divergence and resumes from the last sound point.
- It preserves valid work and avoids both under-correction and overcorrection.
- It distinguishes autonomous detection from changes triggered by user input, tool evidence, or explicit correction.
- It requires corrections to change subsequent behaviour within the available conversation.
- It does not claim to update model weights or provide persistent learning across sessions.
- It retains the visible usage signal but does not treat that signal as evidence of success.
- It does not create a tests directory at this stage; the user explicitly deferred test-folder work.

## Implementation boundary and next work

A skill file can direct the assistant to monitor at meaningful reasoning boundaries and revise before responding. It cannot independently inspect hidden activations, guarantee token-level monitoring, or interrupt arbitrary streaming output. A stronger runtime would need intermediate semantic checkpoints, a monitor, and a controller able to pause, backtrack, and resume. Independent evidence or a verifier would reduce reliance on the generator's own self-assessment.

The skill remains provisional. The next evaluation should seek self-initiated detection in live conversations, distinguish it from user-prompted recovery, and include cases where the correct outcome is to keep the existing trajectory unchanged.
