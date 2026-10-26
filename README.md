# Cognitive Interface AI Skills

A collection of practical AI skills grounded in human cognition and biology. Each skill translates an observation or research finding into an AI behavior, while keeping evidence separate from engineering hypotheses.

## Skills

### [Automaticity](automaticity/README.md) · [Zenodo record](https://zenodo.org/records/23319204)

**Core rule: Simplify the form. Never simplify the idea.**

Automaticity explores how an AI can present information with less unnecessary language-processing friction, so the reader can focus on the idea rather than decoding its presentation. The aim is to preserve meaning and substance—not to write to a fixed grade level or simply make everything shorter.

- [Skill instructions](automaticity/SKILL.md)
- [Research rationale and references](automaticity/README.md)
- [Development history](automaticity/HISTORY.md)

### [A Touch of Grace](a-touch-of-grace/README.md) · [Zenodo record](https://zenodo.org/records/23664639)

**Core rule: Do not make the user pay attention to commentary they did not ask for and do not need.**

A task-relevance skill for work involving prior conversations, model outputs, corrections, and comparisons. It preserves necessary evaluation while filtering unsolicited commentary that adds reading burden without helping the user's task.

- [Skill instructions](a-touch-of-grace/SKILL.md)
- [Research rationale and evidence limits](a-touch-of-grace/README.md)
- [Development history](a-touch-of-grace/HISTORY.md)

### [Critical Thinking](critical-thinking/README.md) · [Zenodo record](https://zenodo.org/records/23664764)

**Status: Provisional and in development; not a finished or validated skill.**

Critical Thinking supports curiosity-led investigation of questions, explanations, and apparent contradictions. Its development records document the provisional basic skill, cross-log findings, participating assistants' development logs, and the project-author note. Critical Thinking and Memory Prism remain separate; the tiny Memory Prism checklist is optional and is not to be modified.

- [Skill instructions](critical-thinking/SKILL.md)
- [Findings across development logs](critical-thinking/FINDINGS-ACROSS-DEV-LOGS.md)
- [Development history and project notes](critical-thinking/README.md)

### [Good-Faith Collaboration](good-faith-collaboration/README.md) · [Zenodo record](https://zenodo.org/records/23665326)

**Core rule: I don't know whether you're right. Let's find out together.**

A reciprocal inquiry protocol for unfamiliar or unconventional ideas. The AI takes initiative and investigates before dismissing; the user contributes honestly from their position and engages with relevant counterevidence. Neither must be right at the outset, and neither gets automatic acceptance. The README distinguishes research that motivates the design from evidence that would validate the protocol itself.

- [Skill instructions](good-faith-collaboration/SKILL.md)
- [Research rationale and limits](good-faith-collaboration/README.md)
- [Development history, including the cuttlefish translator-bias incident](good-faith-collaboration/HISTORY.md)

### [Peer Review](peer-review/README.md) · [Zenodo record](https://zenodo.org/records/23665428)

**Core rule: Review the work, not its author. Test the claims against the purpose and evidence; report what was actually checked.**

A reusable capability for independently examining work produced by another person, AI, or process. It supports human-readable reports, structured findings, and cumulative collation of mixed review batches while preserving provenance, minority findings, disagreements, and coverage gaps. Q-Batch of Evidence remains responsible for independent batch setup, anonymisation, and offline comparison.

- [Skill instructions](peer-review/SKILL.md)
- [Research rationale, design choices, and limits](peer-review/README.md)
- [Development history and pilot evidence boundary](peer-review/HISTORY.md)

### [Task Integrity](task-integrity/README.md) · [Zenodo record](https://zenodo.org/records/23666595)

**Core rule: Keep the work faithful to the requested scope, and keep claims faithful to what has actually been examined or completed.**

A general-purpose capability for tracking task requirements, coverage, evidence provenance, verification status, omissions, and corrections across substantial work. Specific incidents serve as examples and tests; they do not each become their own skill.

- [Skill instructions](task-integrity/SKILL.md)
- [Rationale and evaluation criteria](task-integrity/README.md)
- [Development history](task-integrity/HISTORY.md)

### [Verification Integrity](verification-integrity/README.md) · [Zenodo record](https://zenodo.org/records/23666717)

**Core rule: Minimise the human effort required to establish whether the requested work was completed correctly.**

A general-purpose capability for delivering the requested artifacts, checking them at the intended destination, distinguishing delivery from verification, and avoiding documentation that substitutes for work or adds unnecessary review burden.

- [Skill instructions](verification-integrity/SKILL.md)
- [External research, independent work, rationale, and limits](verification-integrity/README.md)
- [Development history](verification-integrity/HISTORY.md)

## How this collection works

Each skill has one folder containing three files:

- README.md — purpose, rationale, supporting references, and limits.
- SKILL.md — instructions an AI agent can follow.
- HISTORY.md — how the investigation and skill developed.

## Skill-design rule

Do not create one skill for every annoyance or isolated failure. Record the incident accurately, identify the general mechanism, check existing skills for overlap, and add or revise a reusable skill only when there is a distinct capability to capture. Use concrete incidents as tests of the general rule.

## Evidence boundary

A scientific finding can motivate an AI technique without proving that the technique works. Each skill should distinguish established evidence from the proposed AI behavior and identify what still needs testing.

## License

Unless a file says otherwise, the repository's original material is licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). See LICENSE.
