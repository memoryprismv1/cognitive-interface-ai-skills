# History: Peer Review

This history records development and evidence limits. The pilot that prompted this skill is an example, not proof that the skill works.

## 25 October 2026 — Mixed-batch collation for human-readable reports

Added a first-class collation workflow: a mixed batch of review files is classified by the subject actually reviewed, then synthesized into one cumulative readable report per coherent topic. The workflow includes an input-to-report batch index and visible exceptions for unreadable files, uncertain matches, cross-topic inputs, duplicates, and context files. It emphasizes synthesis rather than concatenation, provenance, version boundaries, minority findings, and the distinction between repeated claims and independently checked evidence. See [COLLATION.md](COLLATION.md).

## 25 October 2026 — Generic reports and machine-aggregatable gap discovery

The scope was expanded beyond the original Q-Batch-oriented framing. Any reviewable work or record can be a target, including stories, project plans, single inputs, conversations, logs, and technical artifacts.

The design separates:
- **Review:** one reviewer produces a traceable report.
- **Aggregate:** combine reports for the same target while preserving source findings and reviewer identity.
- **Gap analysis:** organize omissions, contradictions, assumptions, risks, unresolved questions, and areas reviewers did not cover.

The shared report contract separates the human-readable report from structured finding records and includes **Reviewed by** metadata. Aggregation distinguishes convergent, unique, disputed, unresolved, resolved, and rejected findings, and separates gaps in the work from review coverage gaps. Agreement counts are not proof; independence is recorded only when known. Examples illustrate adaptation rather than restricting valid target types. Q-Batch retains its run design, evidence preservation, anonymisation, and offline comparison procedure.

## 22 October 2026 — General capability separated from blind-evaluation procedure

The initial request was for a peer-review skill for AI children. An early draft was placed in the private `self-learning-skills` repository before its intended home and scope had been discussed. It was based on a small Prism-versus-Blind pilot and combined general reviewing with blind-scoring assumptions.

The repository review clarified that `cognitive-interface-ai-skills` is the home for reusable AI behaviours, `q-batch-of-evidence` defines independent batches and comparison, and `self-learning-skills` is for deriving skills from source-linked conversation history. The misplaced draft was removed from the self-learning repository after this version was added; the earlier Git commit remains in that repository's history.

## What the pilot did and did not show

Claude's runner report records four answers: two prompts, one run per prompt in each condition. Both conditions used the same agent and chat. The agent had already read the Q-Batch files, Memory Prism README, and test criteria before producing the answers described as Blind. The source corpus was not opened for the Prism condition, despite the later draft specification proposing that it be loaded.

The observed contrast was narrow: the Prism-conditioned answers proposed competing explanations and a discriminating check; the other answers did not. The pilot cannot establish causation, broad transfer, or reviewer reliability. Its first scoring pass was performed by the same agent that generated the answers and knew the labels. The relabelled copies and scorer brief are a review exercise, not independent validation.

## Research and design decisions

Research on LLM-as-a-judge systems reports position bias, other potential judgment biases, and variation across repeated scoring runs. These motivate criterion-grounded judgments, traceable evidence, disclosure of prior exposure, and caution about single-review verdicts.
- Shi et al. (2025), [Judging the Judges: A Systematic Study of Position Bias in LLM-as-a-Judge](https://aclanthology.org/2025.ijcnlp-long.18/).
- Ye et al. (2025), [Justice or Prejudice? Quantifying Biases in LLM-as-a-Judge](https://proceedings.iclr.cc/paper_files/paper/2025/hash/fdca08d371e4b6c031397909e20043bd-Abstract-Conference.html).
- Haldar & Hockenmaier (2025), [Rating Roulette: Self-Inconsistency in LLM-As-A-Judge Frameworks](https://aclanthology.org/2025.findings-emnlp.1361/).

These studies do not test this skill.

## Current status
Expanded and specified, but not validated. Test varied target types and both individual review quality and aggregation: duplicate detection, minority findings, disagreement, false positives, coverage gaps, traceability, and tracking across revisions. Q-Batch remains responsible for blind-run setup and comparison records.