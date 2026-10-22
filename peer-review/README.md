# Peer Review

**Skill:** `peer-review`

**Purpose:** Help an AI independently examine work produced by another person, AI, or process, and report consequential findings that are traceable to the artifact and its evidence.

**Core rule:** Review the work, not its author. Test the claims against the purpose and evidence; report what was actually checked.

## Why this is a distinct capability

Critical Thinking helps investigate questions and explanations. Task Integrity tracks scope, coverage, provenance, and honest completion claims. Verification Integrity checks concrete deliverables and whether they were actually delivered and checked. Peer Review has a different immediate target: an existing piece of work produced by someone or something else.

It should coordinate with those skills rather than duplicate them. It should also remain useful beyond blind scoring: specifications, research summaries, hypotheses, code, data analyses, and proposed skills can all need independent review.

## Research informing the design

Research on LLM-as-a-judge systems shows that evaluations can be affected by presentation order and other biases, and that scores can vary across repeated runs. This supports a cautious design: use task-relevant criteria, ground findings in the artifact, separate observations from explanations, disclose limits, and do not treat one review as an independent guarantee of correctness.

- Shi, L. et al. (2025). [Judging the Judges: A Systematic Study of Position Bias in LLM-as-a-Judge](https://aclanthology.org/2025.ijcnlp-long.18/). Studies position bias across pairwise and list-wise judgments.
- Ye, J. et al. (2025). [Justice or Prejudice? Quantifying Biases in LLM-as-a-Judge](https://proceedings.iclr.cc/paper_files/paper/2025/hash/fdca08d371e4b6c031397909e20043bd-Abstract-Conference.html). Analyses multiple potential biases in LLM evaluation.
- Haldar, R. & Hockenmaier, J. (2025). [Rating Roulette: Self-Inconsistency in LLM-As-A-Judge Frameworks](https://aclanthology.org/2025.findings-emnlp.1361/). Examines variation in scores across repeated evaluations.

These papers investigate LLM evaluation under particular experimental setups. They motivate safeguards; they do not validate this skill or prove that every review will exhibit the same failure modes.

## Design choices

- Review the artifact itself, not only its author's account of it.
- Apply supplied criteria when suitable; when they are missing, make consequential assumptions visible.
- Tie findings to locations, claims, evidence, and consequences.
- Distinguish confirmed errors, possible issues, and unknowns.
- Do not rewrite, score, rank, or declare a winner unless the task calls for it.
- Use blind-review safeguards only when relevant, and disclose when blinding was compromised.
- Keep the report proportionate to the stakes and the user's requested format.

## Relationship to Q-Batch

[Q-Batch of Evidence](https://github.com/memoryprismv1/q-batch-of-evidence) is a method for independently specified runs, preserved evidence, and offline comparison. It owns batch setup, resource and environment records, anonymisation, and separation of the runner from the scorer. Peer Review supplies a reusable reviewing behaviour when a Q-Batch comparison calls for one; it does not replace the method or its predeclared criteria.

## Evaluation plan

Test this skill on varied artifacts and compare its findings against independent checks. Include cases where the work is sound, has a material error, lacks enough evidence, and is persuasive in style but weak in support. For anonymous comparisons, vary presentation order and record prior exposure. Check both review quality and unnecessary review burden.

## Evidence status and limits

This skill began with a small Prism-versus-Blind pilot in a Claude conversation. That pilot showed a potentially useful contrast in two pairs of answers, but used one run per prompt, the same agent for both conditions, and an evaluator who knew the conditions. The pilot did not test this skill's reliability and cannot establish that the Prism instructions caused the observed differences.

The operational procedure remains a proposal. Its effectiveness, transfer to different artifact types, and effect on human review effort need direct testing.
