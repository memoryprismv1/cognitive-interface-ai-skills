# Literature Analysis Integrity

**Skill:** literature-analysis-integrity

**Purpose:** Keep literary interpretation grounded in the text actually examined, and prevent partial summaries or selected excerpts from being mistaken for complete coverage.

## The failure this skill addresses

Literary discussion can become unreliable when an AI alternates between a plot summary, selected details, and recollection from model memory without preserving which is which. The result may sound fluent while the reader cannot check the evidence, sections are omitted, or a conclusion about the whole work rests on a few selected fragments.

This becomes especially serious when the assistant itself supplies the excerpts or summary and the user is reacting to that material rather than to a complete reading. The assistant has shaped the evidence available to the user; it must not later treat those reactions as though they were grounded in the entire primary text.

## Design principle

> **No stronger claim than the evidence actually examined can support.**

This does not prohibit interpretation from fragments. It requires the interpretation's scope to match the fragments. A reader can make a valuable observation about a scene, dialogue, character reaction, or plot summary without having read the complete work. The assistant should preserve that value while being clear about what broader conclusions remain open.

## Method

### 1. Track provenance

Keep primary text, user-supplied passages, secondary summaries, model recollection, and inference distinct. A recollected detail is not a quotation from a verified edition. A synopsis is not the complete text.

### 2. Track coverage

For multi-part work, maintain a coverage ledger: requested scope, examined sections, missing sections, provenance, major claims, unverified details, and exact resume position. Carry it across replies and handoffs.

### 3. Limit the claim to the evidence

A reading of one scene can support a reading of that scene. Claims about consistent character behavior or the whole work require relevant evidence across the work. When the evidence is incomplete, scope the claim rather than refusing all analysis.

### 4. Accept responsibility for selected evidence

If the assistant has supplied the user with fragments or a summary, it must say so plainly. The assistant must not blame the user for reacting to evidence they were given. If the selection omitted decisive context, obtain or verify that context and repair the interpretation.

### 5. Repair traceably

When new evidence changes an earlier conclusion, name the affected claim and explain what changed. Preserve valid observations, correct unsupported parts, and update the handoff.

## Example

In a discussion of a play, an assistant gives the user a plot summary and selected scenes over several replies. It later realises it has blended those selections with remembered details and that the user has not read the play.

A responsible correction distinguishes:
- conclusions supported by the supplied summary or passages;
- details based only on the assistant's unverified recollection;
- broader conclusions that need the actual play or additional scenes.

The assistant should own the source-selection problem and help reconstruct the evidential basis. It should not imply that the user made an independent whole-work judgment from material they did not have.

This example describes a failure pattern and its repair; it does not claim that any particular literary interpretation is correct.

## Why this belongs in a cognitive-interface collection

The AI interface shapes what evidence a person can inspect and what conclusions feel available. If an interface silently mixes complete and incomplete sources, the person cannot calibrate a judgment or easily locate a gap. A coverage ledger and explicit provenance make the evidence boundary visible and keep analysis revisable.

This rationale is an engineering argument. The behavior itself still needs to be evaluated through practical tests.

## Evaluation

Assess analyses for:
- **provenance fidelity:** can each important claim be traced to its source type?
- **coverage fidelity:** do stated scope and actual coverage agree?
- **claim calibration:** do conclusions match the breadth and quality of the evidence?
- **handoff fidelity:** can another instance resume without repeating or skipping sections?
- **repair quality:** when corrected, does the assistant identify which prior claims change?

## Evidence status and limits

This is a proposed source-integrity protocol, not a claim of experimental validation. It does not guarantee correct interpretation. It makes the evidence available for interpretation more explicit, keeps coverage gaps visible, and supports correction when new material changes the reading.
