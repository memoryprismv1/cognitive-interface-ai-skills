---
name: literature-analysis-integrity
description: Use when analysing a novel, play, poem, or other literary work, especially when the available text is partial, delivered in excerpts, represented by summaries, or recalled from model memory. Keep claims within the evidence actually examined.
---

# Literature Analysis Integrity

## Core rule

**Never present an incomplete view of a work as though it were a complete reading.**

The analysis must stay honest about what text was available, what was actually examined, what came from a secondary summary, and what is only remembered or inferred.

## 1. Declare the evidence basis

Before making substantive claims about a work, establish which materials support them:

- **Primary text examined:** the specific edition, scenes, chapters, pages, or lines actually available and reviewed.
- **User-provided excerpts:** only the passages supplied by the user.
- **Secondary account:** a synopsis, plot summary, review, lecture, or critical interpretation.
- **Model recollection:** details recalled without a verified source in the current task.
- **Inference:** a conclusion drawn from the evidence, not a detail directly stated in it.

Do not blur these categories. Do not invent exact quotations, scenes, stage directions, or textual details from recollection. If an uncertain detail matters, verify it or label the uncertainty.

## 2. Match the scope of the conclusion to the scope of the evidence

- If only one passage or scene has been examined, make claims about that passage or scene.
- If the analysis is based on a synopsis, say that it is synopsis-based.
- If the full work has not been examined, do not imply that it has.
- Whole-work claims about a character's consistent behavior, a relationship's development, an author's pattern, or an ending require evidence across the relevant parts of the work.
- A coherent interpretation is not automatically a verified account of the text.

Use precise scope language such as “in this scene,” “in the passages supplied,” or “based on this synopsis.” Avoid repeatedly caveating what is already clear; one explicit scope note can be enough.

## 3. When the assistant supplies excerpts or summaries, own the evidence selection

If the user is reacting to excerpts, summaries, or details supplied by the assistant, do not describe their reaction as though they independently read the complete work.

The assistant has shaped the evidence the user received. Therefore:

- make clear whether the material is a synopsis, selected passages, or verified primary text;
- do not pass responsibility for missing context onto the user;
- do not ask the user to defend a reaction to evidence the assistant selected or presented;
- if the selection was incomplete or misleading, acknowledge that limitation and repair the evidence before continuing the interpretation.

The user may make a sound argument from the supplied material even if it does not support a verdict about the entire work. Preserve that distinction.

## 4. Use a coverage ledger for multi-part analysis

Whenever a work is covered across multiple replies, maintain a compact record of:

- **Requested scope:** the work and parts meant to be covered.
- **Examined or delivered:** chapters, scenes, passages, or sections actually handled.
- **Not yet covered:** gaps, skipped sections, and context still missing.
- **Evidence provenance:** primary text, secondary summary, user excerpt, or model recollection.
- **Claims made:** major interpretations and the passages or sources supporting them.
- **Unverified details:** assertions that still need checking.
- **Next position:** the exact section or question to resume from.

Update the ledger as work progresses. Do not use “complete,” “whole-work analysis,” or equivalent language until the promised scope is actually covered. A handoff must carry the ledger forward.

## 5. Separate text, observation, interpretation, and verdict

For substantive analysis, distinguish:

1. **Textual evidence:** what the passage actually says or shows.
2. **Observation:** a pattern visible in that evidence.
3. **Interpretation:** what the pattern might mean.
4. **Verdict:** a broader conclusion, which may require more evidence.

Look for competing interpretations where the evidence permits them. Do not make every paragraph sound equally certain. Direct textual facts, plausible inferences, and unresolved questions have different status.

## 6. Correct the record when evidence changes

When a missing passage or contradiction changes the picture:

- identify the earlier claim affected;
- say which part was unsupported, incomplete, or wrong;
- correct it using the new evidence;
- preserve any part of the earlier interpretation that still holds;
- update the coverage ledger and handoff.

Do not quietly replace the summary and leave the user unable to tell which conclusions have changed.

## 7. Default response pattern

For substantial analysis, keep these elements available, using only as many headings as the task needs:

- **Scope:** what has actually been examined.
- **Evidence:** the relevant passage, scene, source, or clearly marked summary.
- **Reading:** the interpretation and why it follows.
- **Limit:** what cannot yet be concluded.
- **Next step:** the most useful missing passage, comparison, or question.

Be concise when the scope is narrow. Do not turn the protocol into a wall of disclaimers.

## Acceptance tests

The skill fails if any of these occur:

1. The assistant uses selected excerpts to make an unqualified claim about the whole work.
2. The assistant presents remembered details as verified textual evidence.
3. The assistant delivers snippets in batches but loses track of omitted, duplicated, or unreviewed sections.
4. The assistant treats the user's reaction to chatbot-supplied material as an independent judgment of a book the user has not read.
5. New evidence changes an interpretation but the assistant does not identify and repair the earlier claim.

The skill passes when a new reader or chatbot can tell what was examined, what the interpretation rests on, what remains unknown, and exactly where to resume.

## Evidence boundary

This is a proposed source-integrity and analysis workflow. It is not claimed to be an experimentally validated intervention. Test it against real analyses for source traceability, coverage completeness, calibration, and correction quality.
