# Peer Review

**Purpose:** Review any work product or record, produce a human-readable report and structured findings, and optionally aggregate multiple reviews into a traceable gap map.

## Anything can be reviewed
Stories, project plans, user inputs, conversations, logs, research, code, datasets, designs, agent outputs, and other artifacts are all valid targets. Examples are illustrative, not a closed list.

## Peer-review collation
Use **`peer-review collate`** (or an equivalent request) for a mixed batch of supplied review files. The agent identifies which files concern which subjects and creates one cumulative human-readable report per topic; the batch need not be pre-sorted. It also creates a batch index mapping each input to its report(s) and an exceptions list for unreadable files, uncertain matches, duplicates, cross-topic files, and context files that are not reviews.

Cumulative means synthesis, not concatenation. Preserve unique and minority findings, disagreements, source provenance, and version differences. Do not treat repeated claims as independent corroboration. See [COLLATION.md](COLLATION.md) for the workflow.

## Two output layers
1. **Human-readable report:** overall assessment, meaningful strengths, important findings, uncertainties, evidence limits, and next steps.
2. **Structured findings:** consistent fields and traceability so different reviewers' findings can be compared and machine-aggregated.

See [REPORT-FORMAT.md](REPORT-FORMAT.md) for the shared report/finding contract and examples.

## Multi-reviewer gap discovery
The aggregator deduplicates findings about the same underlying issue, preserves source reports and reviewer identities, distinguishes convergent findings from unique observations, keeps disagreements visible, and separates defects in the work from **review coverage gaps** (areas no reviewer examined). It can track findings across revisions.

Reviewer count is a signal for prioritization, not proof. Independence must not be assumed, minority findings must not be discarded, and synthesis must not force consensus.

## Relationship to Q-Batch
Q-Batch of Evidence retains its role in independent-run setup, evidence preservation, anonymisation, and offline comparison. Peer Review supplies reusable review behaviour and report structure; it is not limited to Q-Batch experiments.

## Research and evidence status
Research on LLM-as-a-judge systems reports position bias, other judgment biases, and variation across repeated evaluations. These findings motivate traceability and caution but do not validate this skill.
- Shi et al. (2025), [Judging the Judges: A Systematic Study of Position Bias in LLM-as-a-Judge](https://aclanthology.org/2025.ijcnlp-long.18/).
- Ye et al. (2025), [Justice or Prejudice? Quantifying Biases in LLM-as-a-Judge](https://proceedings.iclr.cc/paper_files/paper/2025/hash/fdca08d371e4b6c031397909e20043bd-Abstract-Conference.html).
- Haldar & Hockenmaier (2025), [Rating Roulette: Self-Inconsistency in LLM-As-A-Judge Frameworks](https://aclanthology.org/2025.findings-emnlp.1361/).

The skill remains proposed operational behaviour, not a validated guarantee. Evaluate diverse targets, individual finding quality, aggregation, false positives, minority findings, coverage gaps, traceability, and usefulness.