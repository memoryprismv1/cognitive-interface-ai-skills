---
name: peer-review
description: Independently review any work product or record, produce a human-readable report and structured findings, and optionally aggregate multiple reviews to map gaps without erasing disagreement.
---

# Peer Review

## Core rule
**Review the work, not its author.** Examine it against its purpose, relevant criteria, and available evidence. Report what was actually checked. Review is not automatic agreement, adversarial fault-finding, a rewrite, or proof that the reviewer is correct.

## 1. Any reviewable target
Anything that can be examined as work or a record may be reviewed: a story, project plan, single user input, prompt, conversation, log, research report, code, dataset, design, agent output, or other artifact. This list is illustrative, not restrictive.

Identify the target, version/snapshot and creator when known, the intended use, review purpose, and scope. Use supplied criteria when relevant. If criteria are missing, use the stated purpose and ordinary requirements of the task, making consequential assumptions visible. Adapt the criteria to the target; do not assess a story as if it were a project plan. Ask a focused question if ambiguity prevents a fair review.

## 2. Examine and probe for gaps
Inspect the target itself, not only its author's summary. As appropriate, examine:
- factual support, evidence, provenance, attribution, and uncertainty;
- reasoning, internal consistency, contradictions, and unsupported transitions;
- omissions, unstated assumptions, dependencies, alternatives, counterexamples, edge cases, and failure modes;
- completeness, usability, actionability, and whether consequential steps require guessing;
- whether a final state is supported by a plausible causal sequence when intermediate steps matter.

Adapt to the work. Creative work may invite examination of motivation, continuity, pacing, setup/payoff, point of view, and reader comprehension; distinguish craft judgment from objective inconsistency. Plans may invite examination of ownership, sequencing, dependencies, resources, contingencies, success criteria, and closure. Conversations and logs may invite examination of chronology, attribution, context, claims versus actions, missing steps, and whether conclusions follow from the record. These are prompts, not mandatory checklists. Do not invent flaws to look thorough.

Follow sources or run checks when they materially affect the judgment and tools/access permit it. Distinguish direct observations from explanations and inferences.

## 3. Produce a report with structured findings
Every review should produce a proportionate human-readable report and findings that can be aggregated by a machine. Use [REPORT-FORMAT.md](REPORT-FORMAT.md) as the shared contract.

Report metadata should include, when known: report ID, target identifier/title and version, creator/author, **Reviewed by**, review date, review status, purpose, scope, and criteria. Never invent unavailable metadata.

The report normally contains:
- overall assessment;
- meaningful strengths where useful;
- findings with target location, evidence, consequence, and suggested action/test where possible;
- uncertainties, questions, and disagreements;
- evidence boundary and material limitations;
- recommended next steps where useful.

Each structured finding should include, where applicable: finding ID, type, statement, target locator(s), evidence, impact, epistemic status (e.g. confirmed, suspected, question, disputed), severity/priority, confidence and rationale when useful, suggested action/test, reviewer, and source report. Omit unavailable fields or mark them unknown. Do not require exact locations or numerical confidence where that would create false precision.

## 4. Role boundaries
- Review and report; do not silently edit or take ownership of the source work.
- Keep proposed changes distinct from findings and source material.
- Do not guess the author or hidden instructions.
- Follow blind-review protocols when relevant and disclose compromised blinding.
- Do not score, rank, declare a winner, or issue pass/fail unless requested or appropriate to the task.
- Severity and confidence are judgments, not established facts.
- Repeated agreement is not proof.

## 5. Aggregate multiple reviews (optional operation)
When given multiple reports on the same target, create a consolidated report and gap map.

1. Check target identity and version. Mark version differences; do not silently merge reviews of different versions.
2. Deduplicate by underlying issue, not wording alone. Preserve links to all source reports, reviewers, evidence, and locations.
3. Distinguish:
   - **Convergent findings:** independently raised by multiple reviewers.
   - **Unique findings:** raised by one reviewer.
   - **Disagreements:** incompatible interpretations or recommendations, preserving each rationale.
   - **Unresolved findings:** evidence is insufficient to confirm or reject.
   - **Resolved/rejected findings:** only when evidence and rationale support that status.
4. Treat reviewer counts as a prioritization signal, not proof. Claim independence only when the process establishes it.
5. Preserve minority findings. Different reviewers may have different strengths and blind spots.
6. Identify **review coverage gaps**—areas not examined—separately from suspected defects in the target.
7. Output both a readable synthesis and structured findings; retain source reports unchanged for traceability.
8. On revisions, track findings as open, addressed, partly addressed, disputed, rejected with rationale, or unable to reassess; check for new gaps introduced by the revision.

Do not force consensus or silently edit the target. A human or designated decision-maker may need to resolve disputes.

## 6. Evidence boundary and revisions
Distinguish material inspected directly, second-hand summaries, external/tool checks, unchecked claims, and limitations that could change the conclusion. Keep this proportionate to stakes. When asked to re-review, assess author responses on evidence and reasoning, check the revised artifact, and preserve unresolved disagreement and review history.

## Output default
Use the requested format. Otherwise, produce a proportionate report using the shared structure. The prose is for people; structured findings enable machine aggregation. If no consequential problems were found, say so plainly. Do not manufacture a verdict or paperwork.

## Relationship to other skills
- **Critical Thinking** investigates questions and explanations; Peer Review evaluates an existing target.
- **Task Integrity** tracks scope, coverage, provenance, and completion claims.
- **Verification Integrity** checks concrete deliverables and their destination.
- **Good-Faith Collaboration** governs reciprocal inquiry.
- **Q-Batch of Evidence** owns independent-run setup, evidence preservation, anonymisation, and offline comparison. Peer Review can provide review behaviour and output schema when useful; Q-Batch does not constrain the kinds of work that can be reviewed.

## Evidence status
This is proposed operational behaviour, not a validated guarantee. Research on LLM evaluators motivates safeguards but does not establish that this skill reliably finds gaps. Test it across varied artifact types and compare findings with independent checks.