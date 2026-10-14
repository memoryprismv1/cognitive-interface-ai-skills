# History: Task Integrity

This history records the development of the reusable capability. Specific incidents are retained as examples, not promoted into separate domain-specific skills unless they reveal a genuinely distinct capability.

## 14 October 2026 — From an example to a general mechanism

A user described dissatisfaction with incomplete literary analysis. The supplied material had arrived in pieces, and the assistant had mixed excerpts or summaries with details from unverified recollection. The user had not read the complete work and was reacting to the material the assistant provided.

The example exposed a broader failure: the assistant did not reliably communicate the boundary between requested scope, material actually examined, evidence directly available, and conclusions drawn from that evidence.

The first design response over-specialised the example into a literature-only skill. The user corrected this: literary analysis was an example of a chatbot annoyance, not a request to create a separate skill for every annoyance. The purpose of the repository is a general-purpose skill set.

The design was therefore generalised to Task Integrity: preserve the task contract, track coverage, distinguish evidence provenance, match completion claims to actual work, correct the record traceably, and generalise experiences into reusable capabilities at the appropriate level.

## Design decisions

- The incident remains an example and evaluation case, not the taxonomy for the skill.
- The capability applies across research, coding, file analysis, data analysis, document creation, and extended conversations.
- A task ledger records required, completed, pending, excluded, sourced, unverified, and next-step information when useful.
- The skill library should stay compact. Add a skill for a distinct capability, not every new complaint.
- Incidents must remain accurately attributed. Experiences from separate chatbot interactions must not be merged or blamed on the wrong provider.

## Evidence boundary

This is a record of the observed interaction problem and the engineering generalisation made from it. The broader protocol is a proposal to test, not an experimentally validated intervention.
