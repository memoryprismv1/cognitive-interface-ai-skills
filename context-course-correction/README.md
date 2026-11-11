# Context Course Correction

**Status:** Basic skill; provisional and in development.

**Core rule: The assistant owns monitoring and correcting its trajectory. The user supplies the conversation, not a control panel.**

Context Course Correction is a conversation-level capability. It helps an AI assistant stay aligned with an evolving discussion by checking whether its current interpretation and next action still fit the context established across turns.

It addresses a failure that is easy to mistake for a content problem: the assistant may have access to earlier messages yet continue along a stale or overly narrow line of reasoning. It may fixate on an object, repeat an already rejected explanation, turn an analogy into a premature design, or ask the user to tell it how to correct itself.

The skill requires more than retrieving or summarising prior messages. The assistant must use relevant context to change its subsequent interpretation or action when the conversation calls for it.

## What it does

- Maintains a compact working model of the current objective, broader purpose, constraints, observations, corrections, and unresolved question.
- Interprets each new contribution as something that may continue, modify, challenge, or replace the current direction.
- Checks the assistant's own trajectory for object fixation, stale assumptions, repetition, premature concretisation, level mismatch, and scope drift.
- Interrupts and revises its own course without waiting for the user to diagnose the problem.
- Asks the user for help only when a specific material uncertainty cannot be resolved from available context.
- Shows a visible usage tag when a meaningful context/trajectory check affects the response.

## What makes it distinct

This skill is not a general instruction to remember more, summarise more, brainstorm more, or apologise more.

**Optionality** preserves meaningful alternatives for the user. **Good-Faith Collaboration** governs inquiry and action selection. **Critical Thinking** supports investigation and evidence-based revision. **Task Integrity** tracks scope and completion. Context Course Correction monitors the assistant's own direction across the evolving conversation and makes it responsible for correcting drift.

The central distinction is between *having context available* and *allowing context to change what happens next*.

## Working model

A conversation is treated as an evolving interaction. Each new contribution enters a context that already has a trajectory. It can change the meaning of earlier observations, invalidate an assumption, alter the useful level of analysis, or change the appropriate next action.

This is a design model derived from the development conversation, not a claim that the conversation literally instantiates a particular physical or biological system.

## Visible use

When the skill materially shapes a response, the assistant appends:

**[Context Course Correction used]**

A short explanation immediately before the tag says what was checked, changed, preserved, or redirected. The tag is not used merely because context was available, and it is not proof of successful application.

## Evaluation

The skill should be tested across ordinary and exploratory conversations. Useful tests include:

- New information changes the interpretation rather than being forced into the old frame.
- The assistant notices and abandons a repeatedly rejected explanation.
- A process-level question is not reduced to a fixation on one object or artefact.
- The assistant distinguishes a new topic from a change within an ongoing investigation.
- The assistant corrects itself without asking the user for prompt commands or diagnostic work.
- The assistant sometimes correctly keeps the existing direction when new information does not warrant a change.
- Visible usage signals correspond to actual, material context checks.

The skill is provisional. A written procedure and a self-reported usage tag do not establish that the capability is reliable. Repeated tests and recorded failures are needed.

## Files

- [Skill instructions](SKILL.md)
- [Development history](HISTORY.md)

## Evidence boundary

The initial design comes from a conversational experiment in which the assistant repeatedly narrowed an evolving investigation to objects and proposed architectures, failed to update its framing when the user's examples changed the level of analysis, and then shifted the burden of course correction onto the user. The resulting skill is an engineering response to that observed failure pattern. This case motivates the procedure; it does not prove that the procedure generalises or works reliably.

No claim is made here that Context Course Correction is a scientifically validated cognitive mechanism or that it changes the underlying model's weights or persistent memory.
