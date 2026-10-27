# Development History — Approach Calibration & Help-Seeking

## 2026-10-27 — Initial provisional draft

### Originating question

Can an AI agent judge whether it can manage a task with its current approach, and independently decide when it may need help, without asking for help for everything?

### Design constraints identified

- The agent, not a blanket rule, should decide whether help-seeking is warranted.
- Uncertainty is a signal to evaluate, not an instruction to stop.
- Asking, investigating, changing approach, proceeding with a bounded assumption, and stopping are distinct actions.
- The agent should make progress without transferring ordinary task management to the user.
- It should not keep repeating an ineffective approach merely to avoid asking for help.
- A confidence statement is not proof of calibration; decisions must be compared with observed task performance.
- Easy cases where asking is unnecessary are essential to evaluation.
- The skill should remain provisional until tested.

### Research reviewed

Clarification-seeking, information-gain approaches, and LLM self-correction research provide useful motivation and evaluation ideas. Much of the directly relevant work studies ambiguity in requests, especially coding-agent settings. It does not yet establish general-purpose self-detection of a failing approach and selective human help-seeking.

References and scope notes are maintained in [README.md](README.md).

### Initial implementation

Created:
- `SKILL.md` — operational guidance and failure modes.
- `README.md` — rationale, references, evaluation plan, and limits.
- `HISTORY.md` — provenance and changes.

### Validation status

No controlled behavioural test has yet established the skill's effectiveness. The current artifact is a testable design hypothesis, not evidence that the capability has been acquired.
