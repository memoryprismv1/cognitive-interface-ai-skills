# History: Literature Analysis Integrity

This is a concise reconstruction of the working problem that motivated the skill, not a verbatim transcript.

## 14 October 2026 — Incomplete literary evidence presented in batches

The user reported frustration with a chatbot's literature analysis because it delivered incomplete summaries in successive responses. A screenshot showed an assistant acknowledging a specific problem: it had supplied fragments while also drawing on remembered details; the user had not read the book and was reacting to the evidence the assistant handed over; some details and conclusions therefore could not be checked against the primary text.

The failure was not simply that a summary was short. The assistant controlled the selection of evidence, failed to keep its provenance and coverage sufficiently clear, and then reasoned from that incomplete material as though it gave a reliable basis for the discussion. The user was left reacting to evidence the assistant had selected without a clear way to know what was missing.

This was a distinct incident from the user's separate frustration with premature rebuttal during an unconventional research discussion. The incidents should not be conflated or attributed to one another.

## Design response

The skill requires the assistant to:
- distinguish primary text, supplied excerpts, secondary summaries, recollection, and inference;
- preserve a coverage ledger when material is delivered across multiple replies;
- avoid unqualified whole-work claims from partial coverage;
- take responsibility when the assistant's own selection shaped the user's evidence;
- correct earlier interpretations explicitly when new material changes the picture;
- produce a handoff with the exact coverage and resume position.

## Guiding rule

> **Never present an incomplete view of a work as though it were a complete reading.**

The purpose is not to block literary discussion unless the whole book is available. It is to let partial readings remain useful while preventing them from silently becoming whole-work verdicts.

## Evidence boundary

The originating event is a user-reported experience and screenshot. The workflow is a proposed engineering response. Its effectiveness should be evaluated against real literature analyses for provenance, coverage, calibration, handoff reliability, and repair quality.
