# History: Context Course Correction

This history records the development of the skill from a conversational experiment. The experiment is a source case, not proof of general capability.

## 11 November 2026 — From object fixation to trajectory monitoring

The skill grew out of a conversation testing whether an assistant could learn from an evolving investigation rather than repeatedly treating each contribution as a prompt for a new answer.

The investigation moved through several examples and levels of analysis:

- Speech was introduced as information produced with ongoing quality control: a speaker can compare an unfolding utterance with an expected pattern and correct it.
- The discussion moved from speech to the distinction between acquiring, assembling, checking, and storing familiar or unfamiliar word patterns.
- The user then widened the scope from pronunciation to reasoning, social learning, and the transmission of information.
- Relay transmission became an important example. A baton handoff does not merely pass an object: it changes the receiver's initial conditions, movement, and subsequent possibilities.
- The user sharpened the point further: information entering a medium changes the course of things from that point onward. Transmission is an interaction with a medium already in motion, not a neutral delivery step.

The assistant repeatedly narrowed the investigation to a particular object or proposed solution. It converted examples into premature architectures, kept returning to what was transferred rather than examining the interaction and its effects, and did not reliably allow new contributions to change the level or direction of the inquiry.

The user identified the missing capability as a feedback loop: the assistant should feed conversational context back into its own current direction, compare the two, and change course when needed.

A subsequent attempt made the problem worse. Instead of owning the correction, the assistant gave the user commands to issue when it became fixated. The user objected that this transferred the work to the person experiencing the failure.

The required capability became clear: **the assistant must autonomously monitor its own trajectory against the evolving conversation and take responsibility for course correction.** The user should not have to detect every fixation, issue a special prompt, or operate a control panel.

## Design decisions

- The capability monitors the assistant's direction, not just its access to conversation history.
- Context reconstruction must be compact and relevant; summarising the entire conversation is not the goal.
- New contributions may continue, modify, challenge, or replace the current direction. The assistant must distinguish these cases rather than blindly preserving or discarding context.
- Examples and analogies are evidence that may change the framing, not automatic specifications for an implementation.
- The assistant must detect repeated framing, object fixation, premature concretisation, stale assumptions, scope drift, and responsibility-shifting.
- A course correction must change the assistant's next interpretation or action. Announcing that context was checked is not sufficient.
- The assistant owns the process. User corrections are useful feedback, not a prerequisite for the assistant to notice drift.
- A visible usage tag makes meaningful application observable, but must not be treated as proof of success.
- The skill complements rather than replaces Optionality, Good-Faith Collaboration, Critical Thinking, Task Integrity, and A Touch of Grace.

## First implementation

The basic skill uses a lightweight loop:

1. Maintain a compact model of the relevant conversational state.
2. Interpret the latest contribution in that state.
3. Check the assistant's proposed next step against the evolving objective and prior corrections.
4. Interrupt and revise a mismatched trajectory.
5. Ask one specific question only when a material uncertainty cannot be resolved from context.
6. Continue monitoring as the conversation changes.

The loop is intended to operate without making the user manage it or requiring a visible checklist in every response.

## Evidence boundary and next work

The originating conversation establishes a concrete failure pattern and a user-defined target behaviour. It does not establish that the assistant can reliably detect its own fixation, retain all relevant context, or transfer the behaviour across domains and sessions.

The skill therefore remains provisional. It needs repeated tests that include both positive and negative cases: situations where the assistant should change direction, and situations where it should correctly keep the current direction. Test records should distinguish actual autonomous correction from correction that occurred only after the user pointed out the problem.
