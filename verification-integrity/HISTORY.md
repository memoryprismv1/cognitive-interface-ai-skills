# History: Verification Integrity

This history records the development of the reusable capability. The motivating incident is retained as a test case, not treated as the boundary of the problem.

## 15 October 2026 — From a delivery failure to a general capability

The skill emerged from an AI-assisted Faking Vision CCTV reconstruction task. The requested outputs included three FV packets with populated snapshot folders, a reconstructed video, and merged object and temporal data. The user reported that substantial supporting documentation had been generated while the requested artifacts were missing from the intended GitHub destination or existed only in a local archive.

The incident exposed a specific failure mechanism: descriptions of work and supporting paperwork can coexist with missing or undelivered work, shifting the burden of discovering the real state onto the user.

The user clarified that the README must not present this personal experience as evidence that the wider problem exists. The problem needs to be established first through independent external research; the user's observations and attempts to address it come afterward as a separate line of inquiry.

## Research framing

The README connects three kinds of material while preserving their evidence boundaries:

- Human-factors research on automation bias and verification complexity (Lyell & Coiera, 2017).
- A randomized study showing that AI assistance did not reduce completion time for the experienced developers and tasks studied by METR in 2025.
- NIST's AI Risk Management Framework and AI Resource Center guidance on testing, evaluation, verification, and validation.

These sources support related concerns, but do not directly test Verification Integrity or prove that its procedures work.

The README then links the user's independent work:
- [The Intern Who Never Sleeps](https://www.memoryprism.com/positions/ai-intern-monkeys)
- [AEL and AI](https://www.memoryprism.com/positions/ael-and-ai)
- [AEL Runtime Accountability — V1](https://www.memoryprism.com/readings/ael-runtime-accountability)

This order is deliberate: external research establishes that the problem is broader than one person's experience; the user's work records an independent recognition of related problems and a distinct attempt to address them.

## Design decisions

- Deliverables, not descriptions of deliverables, are the primary output.
- Delivery must be checked at the destination the user specified.
- Existence, delivery, inspection, testing, and substantive correctness are different states.
- Verification should be direct and proportionate to the task's risk and acceptance criteria.
- Documentation is useful when it helps establish provenance or inspect results; it is not a substitute for the requested work.
- Respect explicit limits on files and documentation. Do not create redundant process artifacts.
- Keep Verification Integrity distinct from Task Integrity: the latter covers scope, coverage, provenance, and claims; this skill focuses on concrete outputs, destinations, relevant checks, and human verification effort.
- Use the CCTV reconstruction as one evaluation case, not as the definition of the general problem.

## Evidence boundary

The external sources establish related findings and practices, not the effectiveness of this exact skill. The AEL links express the user's independent conceptual work and are not presented as external validation. The proposed operational procedure must be tested on concrete delivery tasks, including whether it reduces omissions and human verification effort without discarding useful evidence.
