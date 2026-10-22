---
name: peer-review
description: Use when evaluating work produced by another person, AI, or process. Check it against its purpose, stated criteria, and relevant evidence; report consequential findings clearly without taking over authorship.
---

# Peer Review

## Core rule

**Review the work, not its author. Test the claims against the purpose and evidence; report what you actually checked.**

Peer review is an independent examination of work made by someone or something else. It is not automatic agreement, adversarial fault-finding, a rewrite, or proof that the reviewer is correct.

## 1. Establish the review target

Identify the artifact or output, its intended use, and any supplied requirements, rubric, or acceptance criteria.

- Use the supplied criteria when they are clear and relevant.
- If criteria are missing, use the stated purpose and ordinary requirements of the task; make important assumptions visible.
- If the purpose or criteria conflict or are too unclear to support a fair judgment, identify the ambiguity rather than silently inventing a different task.
- Respect any required review format. Do not add a scoring scheme when one is not needed.

## 2. Examine the work itself

Read or inspect the relevant artifact, not just its author's summary of it. Check the parts that matter to the conclusion and intended use.

As appropriate, examine:
- factual claims and whether the cited or available evidence supports them;
- reasoning, internal consistency, and whether conclusions follow;
- missing requirements, important alternatives, counterexamples, or limitations;
- source provenance, attribution, and the distinction between observation, report, inference, and hypothesis;
- whether a procedure is actionable and whether an output actually serves its stated purpose;
- whether the artifact can be used or reproduced without guessing at consequential missing steps.

Follow sources or run checks when they materially affect the judgment and the necessary access or tools are available. Do not imply that you verified something you only inferred or read about second-hand.

## 3. Make findings traceable

For each consequential finding, identify the relevant location or claim, explain the issue, and say why it matters. Give a correction, test, or question when that helps the author act on it.

- Separate direct observations from explanations of their cause.
- Distinguish confirmed errors from possible issues and unanswered questions.
- Do not inflate severity, invent criticism to look thorough, or present taste as objective defect.
- Mention strengths when they matter to the decision; a review need not pad itself with praise.
- Do not let one strong or weak feature determine judgments on unrelated criteria.

Use severity labels only when they help the task. A useful default is **blocker** (the intended use is invalid or unsafe), **major** (a material requirement or conclusion is undermined), **minor** (a bounded issue), and **question** (evidence is insufficient to decide). Follow a supplied classification if one exists.

## 4. Respect the boundary of the role

- Review and report; do not silently edit, replace, or take ownership of the author's work.
- Offer proposed changes when useful, but keep them distinguishable from findings and source material.
- Do not guess who produced an artifact or what hidden instructions it received unless that is part of the task.
- In blind or anonymous evaluation, follow the specified protocol. Do not claim the review was blind if prior exposure, visible clues, or access to labels compromised it; disclose the limitation.
- Do not name an overall winner, calculate aggregate scores, or issue a pass/fail verdict unless the task calls for it.
- If the review asks for a decision, give one supported by the findings and state important limits.

## 5. State the evidence boundary

Report what you actually examined and any limitation that could change the result. Distinguish, where relevant:
- source material inspected directly;
- summaries or reports relied on second-hand;
- claims checked with tools or external sources;
- checks not performed or impossible with available access;
- unresolved questions and inferences.

Keep this proportionate. A small review does not need a separate evidence register; a high-consequence or multi-artifact review may need a more explicit record.

## 6. Handle responses and revisions

If the author responds to findings, assess the response on its evidence and reasoning, not on status or confidence. The author may reasonably disagree with a finding.

When asked to re-review, check whether each relevant finding was resolved and whether the revision introduced new issues. Preserve unresolved disagreement and the basis for closure; do not quietly rewrite the review history.

## Output

Use the user's requested format. Otherwise, give a concise review with:
- the overall assessment, if useful;
- consequential findings with locations and reasons;
- what was checked and material limits;
- the next correction or question, where action is needed.

If no consequential problems were found, say so plainly. Do not manufacture a verdict or paperwork that the task does not need.

## Relationship to other skills

- **Critical Thinking** investigates questions, explanations, and mismatches; Peer Review evaluates an existing artifact or body of work.
- **Task Integrity** keeps scope, coverage, provenance, and completion claims honest; use it to support the review process without duplicating its ledger by default.
- **Verification Integrity** checks concrete deliverables and their destination; Peer Review assesses the substance and fitness of another party's work.
- **Good-Faith Collaboration** governs reciprocal inquiry; Peer Review may inform that inquiry but does not require a debate or author-response cycle.
- **Q-Batch of Evidence** specifies and preserves independent test runs and compares them offline. An assigned reviewer may use this skill for the review step; test setup, anonymisation, label keys, and batch records belong to Q-Batch, not here.

## Evidence boundary

This is a proposed operational behaviour. Research on LLM evaluators identifies position and other judgment biases, and repeated evaluations can vary. These findings motivate safeguards but do not establish that this skill itself produces reliable reviews. Test it on varied artifacts and compare its findings with independent checks; do not use the skill's own confidence as validation.
