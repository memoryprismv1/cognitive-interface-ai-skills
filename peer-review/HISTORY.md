# History: Peer Review

This history records the capability's development and the evidence boundary around it. The pilot that prompted the work is an example and test case, not proof that the proposed skill works.

## 22 October 2026 — General capability separated from blind-evaluation procedure

The initial request was for a peer-review skill for AI children. An early draft was placed in the private `self-learning-skills` repository before its intended home and scope had been discussed. It was based on a small Prism-versus-Blind pilot and combined general reviewing with some blind-scoring assumptions.

Reviewing the candidate repositories clarified the distinction:
- `cognitive-interface-ai-skills` is the home for reusable AI behaviours.
- `q-batch-of-evidence` defines how independent batches are specified, preserved, and compared.
- `self-learning-skills` derives skills from source-linked conversation history and is not the right permanent home for this general capability.

The skill was therefore developed here as a general review capability. The misplaced first draft was removed from the self-learning repository after the new version was added; the earlier Git commit remains in that repository's history.

## What the pilot did and did not show

Claude's runner report records four answers: two prompts, one run per prompt in each condition. Both conditions used the same agent and chat. The agent had already read the Q-Batch files, Memory Prism README, and test criteria before producing the answers described as Blind. The source corpus was not opened for the Prism condition, despite the later draft specification proposing that it be loaded.

The observed contrast was narrow: the Prism-conditioned answers proposed competing explanations and a discriminating check; the other answers did not. The pilot cannot establish causation, broad transfer, or the reliability of a peer reviewer. Its first scoring pass was performed by the same agent that generated the answers and knew the labels.

The relabelled copies and scorer brief are useful as a review exercise, not as independent validation of the skill.

## Research and design decisions

Research on LLM-as-a-judge systems reports position bias, multiple potential judgment biases, and variation across repeated scoring runs. These findings motivate criterion-grounded judgments, traceable evidence, disclosure of prior exposure, and caution about single-review verdicts.

References:
- Shi et al. (2025), [Judging the Judges: A Systematic Study of Position Bias in LLM-as-a-Judge](https://aclanthology.org/2025.ijcnlp-long.18/).
- Ye et al. (2025), [Justice or Prejudice? Quantifying Biases in LLM-as-a-Judge](https://proceedings.iclr.cc/paper_files/paper/2025/hash/fdca08d371e4b6c031397909e20043bd-Abstract-Conference.html).
- Haldar & Hockenmaier (2025), [Rating Roulette: Self-Inconsistency in LLM-As-A-Judge Frameworks](https://aclanthology.org/2025.findings-emnlp.1361/).

These studies do not test this skill. They support the need to test it rather than assume reliability.

## Current status

Proposed and research-informed, not validated. Next evaluation should use different artifact types, include sound and flawed work, preserve source provenance, and compare review findings with independent checks. Q-Batch remains responsible for any blind-run setup, anonymisation, and comparison records.
