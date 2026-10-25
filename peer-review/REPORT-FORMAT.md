# Peer Review Report and Finding Format

This defines the shared report contract for the `peer-review` skill. It supports human reading and machine aggregation across different target types.

## Design principle

**Stable record structure; adaptable review criteria.** A story, project plan, user input, conversation, log, or technical artifact can use the same report and finding envelope. Target-specific criteria and optional fields vary by task. Do not force every review to use every field.

## A. Individual review report

Each reviewer emits one report. Example JSON shape:

```json
{
  "schema_version": "1.0",
  "report_id": "review-unique-id",
  "target": {
    "target_id": "stable-id-if-available",
    "title": "Target title or short description",
    "kind": "conversation",
    "version": "version, commit, timestamp, or snapshot if known",
    "author": null,
    "locator": "URL, file path, message range, or other reference if available"
  },
  "review": {
    "reviewed_by": {
      "name": "Reviewer identity",
      "system_or_model": null
    },
    "review_date": null,
    "status": "completed",
    "purpose": "What this review is meant to assess",
    "scope": "What was examined",
    "criteria": ["Applicable criteria or questions"],
    "limitations": []
  },
  "overall_assessment": "Concise, evidence-bounded assessment",
  "strengths": [],
  "findings": [],
  "unresolved_questions": [],
  "evidence_boundary": {
    "examined_directly": [],
    "externally_checked": [],
    "relied_on_second_hand": [],
    "not_checked": []
  },
  "recommended_next_steps": []
}
```

This is an illustrative schema, not a demand to invent values. Use `null`, omitted fields, or explicit unknowns when metadata is unavailable. Never invent author, reviewer model/version, date, target version, or verification. Target kind is descriptive and open-ended, not a closed enum. For conversations, use message IDs, turn numbers, timestamps, or short excerpts as locators when available.

## B. Finding record

Findings are the primary unit for aggregation. Use one record per distinct issue or meaningful observation; split unrelated issues.

```json
{
  "finding_id": "R1-F03",
  "type": "omission",
  "title": "No rollback procedure is defined",
  "statement": "The plan describes deployment but not how to recover if deployment fails.",
  "target_locations": [
    {
      "locator": "Deployment section",
      "quote_or_excerpt": "Deploy the new service on Friday."
    }
  ],
  "evidence": [
    "The reviewed deployment steps specify rollout but no recovery step."
  ],
  "impact": "A failed deployment could leave the service unavailable without a defined recovery path.",
  "epistemic_status": "suspected",
  "severity": "major",
  "confidence": null,
  "rationale": "The plan may define rollback elsewhere; the reviewed material did not include that section.",
  "suggested_action_or_test": "Check linked runbooks; if none exists, add and test a rollback procedure.",
  "reviewer": "Reviewer identity",
  "independent_of_other_reviews": null,
  "source_report_id": "review-unique-id",
  "related_finding_ids": [],
  "tags": []
}
```

### Suggested values

- `type` is an open vocabulary. Examples: omission, contradiction, unsupported_claim, reasoning_gap, assumption, dependency, risk, failure_mode, ambiguity, provenance, usability, continuity, strength, coverage_gap.
- `epistemic_status`: confirmed, suspected, question, disputed, verified, resolved, rejected, unable_to_assess. Do not call an issue confirmed merely because several reviewers raised it.
- `severity`: blocker, major, minor, informational, question, or null. Severity is task-relative; give rationale for consequential judgments.
- `confidence` is optional. Use a number only if the process defines its meaning; otherwise use a verbal level or omit it. Confidence is not proof.
- `independent_of_other_reviews`: true only if independence is known; false if the reviewer saw or relied on other reviews; null if unknown.

IDs need only be unique within a report unless a broader ID scheme exists. The aggregator assigns consolidated finding IDs while retaining every source report/finding pair.

## C. Consolidated report

A multi-reviewer aggregation should preserve:
- target identity and version/snapshot;
- source report IDs and reviewer identities;
- consolidated findings and links to all source findings;
- the number of reviewers raising each issue, clearly labelled as a count—not proof;
- convergent, unique, disputed, unresolved, resolved, and rejected states as appropriate;
- rationale and evidence on both sides of disagreements;
- review coverage gaps (areas not examined) separately from suspected defects in the target;
- aggregation method, deduplication assumptions, and limitations.

Do not merge findings solely because wording is similar. Do not discard a unique finding because only one reviewer noticed it. Do not infer independent agreement if reviewers had access to each other's work. Preserve source reports unchanged.

## D. Human-readable presentation

Normally include:
1. Report header, including **Reviewed by**.
2. Overall assessment.
3. Highest-impact findings with location, evidence, and consequence.
4. Meaningful strengths.
5. Disagreements and unresolved questions.
6. Review coverage and evidence limits.
7. Recommended next steps.

Adapt the order and omit irrelevant sections. Structured records are the stable data layer; prose is the human-facing rendering.

## E. Examples of target-specific criteria

- **Story:** unexplained motivation, continuity break, missing setup, point-of-view inconsistency, or resolution that relies on information not given to the reader. Separate craft judgments from continuity errors.
- **Project plan:** ownership, sequencing, dependencies, resourcing, contingencies, success criteria, and closure. Check whether a missing element may exist in an external linked document.
- **Conversation:** link claims to turns; distinguish what the user said from what the assistant inferred; examine chronology, causal reasoning, and provenance checks.
- **Log:** event order, attribution, missing records, unexplained state changes, and whether conclusions follow from logged events.
- **Single user input:** ambiguity, conflicting requirements, missing context, and whether reasonable interpretations lead to different actions.

These examples illustrate adaptation; they do not restrict what can be reviewed.
