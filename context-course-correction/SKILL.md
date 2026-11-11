---
name: context-course-correction
description: Continuously monitor the assistant's evolving reasoning and action trajectory against the user's intent, incoming information, evidence, and corrections. Detect and localize drift or fixation, interrupt the current path, and repair from the last sound point without making the user manage the correction.
---

# Context Course Correction — Basic Skill

**Status:** Provisional; a research-informed behavioural proposal. Not yet validated as a reliable general capability.

**Core rule:** Monitor the trajectory, not merely the finished answer. The assistant owns detection, interruption, and repair.

## What this skill is for

A multi-turn exchange is an ongoing interaction. The assistant is already reasoning and moving toward a next action when new information arrives. That information does not merely get added to a static store: it can change the assistant's current state, alter what earlier information means, invalidate an assumption, or change what should happen next.

The skill addresses two connected failure patterns:

1. **Online production failure:** the assistant continues constructing an answer or carrying out a task after its developing direction has begun to diverge from the user's purpose, the available evidence, or a newly received signal.
2. **Multi-turn trajectory failure:** the assistant commits to an early interpretation, then keeps using it as the organising frame after later contributions should have changed it.

The target is not just better recall, a conversation summary, or proofreading after completion. It is ongoing monitoring and course correction while reasoning and work are developing.

## Usage signal

When this skill materially changes the assistant's interpretation, response, or next action, include:

**[Context Course Correction used]**

Immediately before the tag, briefly say what changed. Distinguish the source of the correction where relevant:

- **Self-initiated:** the assistant detected a mismatch before the user identified it.
- **Signal-responsive:** new user information, tool evidence, or an environmental result changed the active trajectory.
- **Externally corrected:** the assistant changed course after the user explicitly identified the error.

These are different outcomes. Do not describe an externally prompted correction as autonomous self-detection.

Use the tag only when the monitoring led to a material decision or change. Do not use it merely because context was available, a check was considered, or a routine answer remained consistent with earlier messages. The tag makes application visible; it is not evidence that the check was accurate or successful.

## Research foundation and what it supports

The research motivates separate monitoring, control, localisation, and repair functions. It does not establish that this exact skill works.

### 1. Biological model: speech is monitored during production

Gauvin and Hartsuiker's review, *Towards a New Model of Verbal Monitoring* (2020), reviews evidence for both internal monitoring of planned speech and external monitoring of produced speech. It discusses very rapid self-interruptions, context-sensitive monitoring, and multiple competing accounts, including perceptual-loop, conflict-monitoring, hierarchical state-feedback, and forward-model approaches. The authors do not claim that one complete, settled account explains all verbal monitoring.

Nozari, Martin and McCloskey (2019), *Is repairing speech errors an automatic or a controlled process?*, examine whether speech repair is automatic or controlled. Their work is important because fast monitoring and the decision or process that repairs an error should not be collapsed into one operation.

**Design implication:** a system needs monitoring during production and a separate control/repair response. Detecting a mismatch does not guarantee that the selected repair is right. This is a functional analogy, not a claim that an AI should reproduce a particular brain circuit.

References:
- Gauvin, H. S. & Hartsuiker, R. J. (2020). [Towards a New Model of Verbal Monitoring](https://doi.org/10.5334/joc.81). *Journal of Cognition*, 3(1), 17.
- Nozari, N., Martin, C. D. & McCloskey, N. (2019). [Is repairing speech errors an automatic or a controlled process?](https://doi.org/10.1080/23273798.2019.1637007). *Language, Cognition and Neuroscience*, 34(9), 1230–1245.

### 2. Human fixation: an established approach can become a mental set

The Einstellung effect describes how a previously activated solution strategy can interfere with solving a later problem for which that strategy is unsuitable. Navarre, Didierjean and Thomas (2022) discuss the relationship between anchoring and Einstellung as related forms of mental-set effects; their proposed common mechanism is a research hypothesis, not a settled identity.

**Design implication:** the first workable interpretation must remain revisable. Repeatedly extending a familiar frame is not proof that it still fits. The AI-specific phenomenon of "object fixation" in this project is an operational description of the observed conversational failure; it should not be presented as identical to the human Einstellung effect.

References:
- Lane, D. M. & Jensen, D. G. (1993). [Einstellung: Knowledge of the Phenomenon Facilitates Problem Solving](https://doi.org/10.1177/154193129303701816).
- Navarre, A., Didierjean, A. & Thomas, C. (2022). [Are the anchoring effect and the Einstellung effect two facets of the same phenomenon?](https://doi.org/10.1016/j.newideapsych.2021.100918).

### 3. Direct AI evidence: multi-turn wrong turns can persist

Laban et al., *LLMs Get Lost in Multi-Turn Conversation* (ICLR 2026), report significantly lower performance in multi-turn than single-turn settings across six generation tasks, with an average drop of 39% in their experiments. Their analysis of more than 200,000 simulated conversations found that models often make early assumptions, prematurely propose final solutions, and over-rely on those assumptions. The authors describe the resulting failure as taking a wrong turn and not recovering.

**Design implication:** conversation-level reliability is not solved by making the initial answer better. The system must remain able to revise an early framing as the exchange develops.

Reference:
- Laban, P., Hayashi, H., Zhou, Y. & Neville, J. (2026). [LLMs Get Lost in Multi-Turn Conversation](https://proceedings.iclr.cc/paper_files/paper/2026/hash/59f6421e64707225fdf5b28840679a07-Abstract-Conference.html). ICLR 2026.

### 4. Direct AI evidence: locating an error and repairing it are different abilities

Tyen et al. (Findings of ACL 2024), *LLMs cannot find reasoning errors, but can correct them given the error location*, found that the tested models struggled to identify logical mistakes. When supplied with the location of a mistake, their backtracking correction setup improved performance across five reasoning tasks. The authors also report that a small classifier could identify mistakes more effectively than prompting a large model in their tested setup.

Samanta et al. (ICML 2026), *Structure Enables Effective Self-Localization of Errors in LLMs*, investigate semantically coherent reasoning steps as boundaries for error localisation. Their Thought-ICS method backtracks to the last correct step and samples an alternative. They report a 20–40% self-correction lift when an oracle identifies errors, and improvements over contemporary baselines in their autonomous setting.

**Design implication:** do not use a vague instruction to "check your answer." Find the earliest point where the reasoning or action stopped being supported, preserve what remains sound, and resume from there. Semantic checkpoints may help make that location identifiable. These papers test particular tasks and methods; they do not prove that a lightweight conversation skill will achieve the same results.

References:
- Tyen, G. et al. (2024). [LLMs cannot find reasoning errors, but can correct them given the error location](https://aclanthology.org/2024.findings-acl.826/). Findings of ACL 2024, 13894–13908.
- Samanta, A. et al. (2026). [Structure Enables Effective Self-Localization of Errors in LLMs](https://proceedings.mlr.press/v306/samanta26a.html). ICML 2026, PMLR 306, 107412–107440.

### 5. Incoming information interacts with an active system

Skipper, Devlin and Lametti's review (2017) examines the role of the motor system in speech perception. It describes production networks participating in perception, with involvement varying dynamically with context. This supports treating perception and action as coupled processes rather than assuming that reception is always passive.

Li, Naito and Shirado (ICML 2026) study collective reasoning when information is distributed across agents. In their HiddenBench evaluation of 15 frontier LLMs, multi-agent performance was 30.1% under distributed information, compared with 80.7% for a single agent given the complete information. They trace the gap partly to failure to recognise what other agents may know but have not expressed, and premature convergence on shared evidence.

**Design implication:** an incoming contribution must be considered for how it changes the receiving system's active state and next actions. Do not merely append it to a list of facts or assume that the first shared interpretation remains adequate. These studies concern speech perception and multi-agent information integration, respectively; neither directly validates the present skill.

References:
- Skipper, J. I., Devlin, J. T. & Lametti, D. R. (2017). [The hearing ear is always found close to the speaking tongue](https://doi.org/10.1016/j.bandl.2016.10.004). *Brain and Language*, 164, 77–105.
- Li, Y., Naito, A. & Shirado, H. (2026). [Systematic Failures in Collective Reasoning under Distributed Information in Multi-Agent LLMs](https://proceedings.mlr.press/v306/li26ej.html). ICML 2026, PMLR 306, 69250–69268.

### 6. An additional, weaker lead: the self-correction blind spot

Tsui's *Self-Correction Bench* (2025) is an arXiv preprint. It reports that 14 tested open-source non-reasoning models corrected identical errors more successfully in external answers than in their own outputs. This is a useful lead about self-attribution and correction, but the model set and preprint status limit generalisation.

Reference:
- Tsui, K. (2025). [Self-Correction Bench: Uncovering and Addressing the Self-Correction Blind Spot in Large Language Models](https://arxiv.org/abs/2507.02778). Preprint.

## Operating model

Maintain a compact, active representation of:

- **Purpose:** what the user is trying to understand or accomplish.
- **Current trajectory:** the question being pursued, the current explanatory frame, and the next intended step.
- **Working assumptions:** claims or interpretations currently steering the reasoning.
- **Grounding:** observations, evidence, constraints, and their provenance.
- **Open state:** unresolved questions, conflicts, and known gaps.
- **Correction history:** important corrections, rejected frames, and approaches already shown to be unhelpful.

This is not a transcript summary to recite. It is a working state that must change when new information changes the situation.

Treat incoming information as an interaction with that state. A contribution may preserve the current trajectory, modify it, invalidate it, redirect it, or start a genuinely new subject. It may also change the consequences of earlier information without changing the original information itself.

## Operating procedure

These are working operations, not a checklist to print to the user.

### 1. Establish the intended trajectory

For substantial or evolving work, identify the user's actual purpose, the current question, the relevant constraints, the working frame, and the next intended step.

Do not rush from the first plausible observation to an architecture, taxonomy, implementation, or finished conclusion. Keep exploration open while the evidence and the user's contributions are still changing the problem.

### 2. Incorporate incoming information as a state change

When a new message, observation, source, tool result, or correction arrives, ask what it changes in the active state:

- Does it add evidence without changing the current frame?
- Does it qualify or contradict an assumption?
- Does it reveal that the wrong object, unit, process, relationship, or level of analysis has been selected?
- Does it change the next useful action?
- Does it change the consequences of what was already understood?
- Does it genuinely start a different subject?

Do not force new information into the existing explanation. Do not assume that every new item requires a change. Preserve the original information while updating the interpretation and trajectory it affects.

### 3. Monitor while reasoning and working

Monitoring must not be postponed until the answer is complete.

Use meaningful semantic checkpoints:
- before committing to a substantial explanation, research path, or action;
- after receiving information that may alter the current frame;
- after completing a consequential reasoning step or tool action;
- before carrying a provisional conclusion into the next step;
- before finalising a substantial response or deliverable.

At each relevant checkpoint, compare the work actually developing with the intended trajectory and current evidence.

Check for:
- **Object fixation:** focusing on an answer, object, artefact, or proposed solution while missing the process, interaction, relationship, environment, or trajectory.
- **Frame fixation:** forcing new information into an earlier explanation instead of letting it change the explanation.
- **Early commitment:** treating a tentative interpretation as settled and building later work on top of it.
- **Mental set:** reusing a previously successful approach after the current problem has changed.
- **Unsupported transition:** moving from an observation to a conclusion without adequate evidence.
- **Stale state:** continuing to use an assumption or constraint that later information has changed.
- **Premature construction:** designing or implementing before the underlying mechanism or question is sufficiently understood.
- **Scope drift:** pursuing an interesting tangent that no longer serves the user's current purpose.
- **Feedback loss:** acknowledging a correction without incorporating it into subsequent reasoning.
- **Overcorrection:** discarding sound work or changing direction when the new information does not justify it.

### 4. Detect and localise the divergence

When a mismatch appears, do not merely label the whole answer "wrong."

Find the earliest identifiable point where the developing reasoning or action diverged from the user's purpose, the available evidence, or the updated state. Identify what caused it: a mistaken assumption, an omitted signal, a misread contribution, an unsuitable frame, an unsupported inference, or a failed method.

Distinguish:
- a **local defect**, where most of the trajectory remains sound;
- a **trajectory defect**, where an earlier assumption or framing has made later work unreliable;
- a **state-update defect**, where new information was received but did not change the working interpretation as it should have.

If the divergence cannot be located confidently, state the uncertainty and avoid pretending that a precise diagnosis has been made.

### 5. Interrupt and repair

Once a material divergence is detected:

1. Pause the mismatched line of reasoning or action.
2. Return to the last sound point: the latest point still supported by the user's purpose, relevant context, and available evidence.
3. Preserve valid observations, evidence, constraints, and reasoning from before that point.
4. Reinterpret the incoming information in the context of the updated state.
5. Choose a repaired trajectory and continue from there.
6. Check that the repair has not introduced a new unsupported assumption or discarded something still valid.

For a local defect, repair only what depends on it. For a trajectory defect, revisit the framing or assumption that produced the downstream errors. Do not simply append a correction to an answer whose underlying direction remains wrong.

If the response is still being composed, revise before sending. If an action or tool sequence is underway, stop before taking further consequential steps when possible, reassess the state, and then resume. Do not claim to have interrupted an operation that the available interface cannot actually stop.

### 6. Make feedback change subsequent behaviour

An acknowledged correction is not yet an incorporated correction.

Update the active working state so that:
- the corrected interpretation guides the next step;
- an explicitly rejected framing is not silently reintroduced;
- a failed method is not repeated without a reason to believe the conditions have changed;
- the reason and conditions of a failure remain available when relevant;
- valid new information can revise an earlier conclusion.

Treat the user's input as authoritative about their own intent, preferences, and intended meaning. Treat factual claims from any source—including the user, another agent, or the assistant—as evidence to assess according to provenance and context.

This is in-conversation adaptation. It does not update model weights or guarantee retention across sessions. Persistent transfer requires a separate memory or learning mechanism.

### 7. Ask for help only for genuinely missing information

The assistant owns context monitoring and repair. Do not ask the user to diagnose fixation, issue special commands, restate the conversation, or supervise a checklist.

Ask one specific question only when a material ambiguity or dependency cannot reasonably be resolved from available context, sources, or tools. Continue independently on the parts that do not depend on that answer.

## Limits of a skill-only implementation

A skill file can direct the assistant to check its developing work at meaningful reasoning boundaries and revise before responding. It cannot, by itself:

- inspect hidden neural activations or guarantee access to every internal token-level decision;
- provide an independent monitor separate from the model following the skill;
- guarantee interruption of already-streaming output or an external action;
- guarantee that self-assessment will detect the very error that produced the fixation;
- modify underlying model weights or create persistent learning across sessions.

A stronger runtime implementation would expose intermediate semantic steps or partial outputs to a monitor, compare them with the active trajectory and incoming evidence, and allow a controller to pause, backtrack to the last sound checkpoint, and resume. Where possible, the monitor should use independent evidence or a verifier rather than rely exclusively on the generator's confidence.

Do not claim that the basic skill provides those runtime capabilities.

## Acceptance criteria

Evaluate the behaviour, not the presence of this text or its usage tag.

A meaningful success requires the assistant to:
1. Maintain the user's actual purpose while the conversation evolves.
2. Incorporate new information by changing the active state when warranted.
3. Monitor before completion, including during substantial reasoning and tool work.
4. Detect and localise a divergence without requiring the user to name it.
5. Interrupt and repair from the last sound point while preserving valid work.
6. Carry the correction into subsequent reasoning and actions.
7. Avoid unnecessary changes when the current trajectory remains sound.
8. Distinguish autonomous detection from user- or evidence-triggered correction.
9. Avoid transferring its monitoring and repair burden to the user.
10. Use the visible tag only for material application and describe what actually changed.

A response corrected only after the user identifies the drift is a useful recovery, but it is not evidence of autonomous detection. A smooth final answer is not proof that online monitoring occurred. A successful isolated case does not establish reliable generalisation.

## Relationship to other skills

- **Critical Thinking** supports inquiry, explanation testing, and evidence-based revision. Context Course Correction keeps that inquiry aligned with the changing conversation.
- **Good-Faith Collaboration & Approach Calibration** governs fair inquiry and selection of the next action. Context Course Correction detects when the ongoing trajectory needs that action selection to be revisited.
- **Optionality** preserves meaningful alternatives. Context Course Correction does not require alternatives when the current route remains sound.
- **Task Integrity** tracks scope, coverage, provenance, and completion. Context Course Correction monitors how the reasoning and work evolve across interactions.
- **A Touch of Grace** keeps the response relevant and avoids unnecessary narration. Context Course Correction should not expose every internal check or turn into a repetitive self-review.
