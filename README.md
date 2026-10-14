# Cognitive Interface AI Skills

A collection of practical AI skills grounded in human cognition and biology. Each skill translates an observation or research finding into an AI behavior, while keeping evidence separate from engineering hypotheses.

## Skills

### [Automaticity](automaticity/README.md)

**Core rule: Simplify the form. Never simplify the idea.**

Automaticity explores how an AI can present information with less unnecessary language-processing friction, so the reader can focus on the idea rather than decoding its presentation. The aim is to preserve meaning and substance—not to write to a fixed grade level or simply make everything shorter.

- [Skill instructions](automaticity/SKILL.md)
- [Research rationale and references](automaticity/README.md)
- [Development history](automaticity/HISTORY.md)

### [Good-Faith Collaboration](good-faith-collaboration/README.md)

**Core rule: I don't know whether you're right. Let's find out together.**

An inquiry protocol for responding to unfamiliar or unconventional ideas: reconstruct the user's claim, identify concrete tests, investigate before rebutting, and weigh supporting and contradicting evidence. The README distinguishes the proposed AI behavior from claims that would need empirical validation.

- [Skill instructions](good-faith-collaboration/SKILL.md)
- [Research rationale and limits](good-faith-collaboration/README.md)
- [Development history](good-faith-collaboration/HISTORY.md)

## How this collection works

Each skill has one folder containing three files:

- `README.md` — what the skill is for, its rationale, supporting references, and limits.
- `SKILL.md` — the instructions an AI agent can follow.
- `HISTORY.md` — how the investigation and skill developed.

No separate research archive or nested documentation structure: the relevant material stays with its skill.

## Evidence boundary

A scientific finding can motivate an AI technique without proving that the technique works. Each skill should distinguish established evidence from the proposed AI behavior and identify what still needs testing.

## License

Unless a file says otherwise, the repository's original material is licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). See [`LICENSE`](LICENSE).
