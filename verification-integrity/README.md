# Verification Integrity

**Zenodo record:** [Archived release](https://zenodo.org/records/23666717)

**Skill:** `verification-integrity`

**Purpose:** Make it easier to establish whether an AI completed the requested work correctly, without forcing the user to reconstruct the task from claims, paperwork, and scattered artifacts.

**Core rule:**

> **Minimise the human effort required to establish whether the requested work was completed correctly.**

## 1. The wider problem: automation creates verification work

The problem is not unique to one user, project, or AI system. Research on human interaction with automation has long examined the risk that the system's output becomes easier to accept than to check. Newer AI tools add a related practical concern: generating output can be fast while reviewing, correcting, integrating, and validating it remains expensive.

These bodies of work are related, but they do not all study the same phenomenon. The distinctions matter.

### Verification complexity and automation bias

Lyell and Coiera's systematic review, *Automation bias and verification complexity* (2017), examined 40 studies selected from 890 papers. It found evidence of automation bias in both single-task and multitask settings, with the single tasks showing automation bias tending to involve higher verification complexity. The authors describe verification complexity in terms of the steps needed to assess whether automation is functioning correctly. They also stress that the literature was fragmented and that relatively few studies reported statistical significance against a non-automated control.

This research establishes that **checking automation can itself be cognitively demanding**, and that this difficulty is relevant to whether people notice or rely on errors. It does not directly study AI-generated project deliverables or prove the effectiveness of this skill.

Reference: Lyell, D. & Coiera, E. (2017). [Automation bias and verification complexity: a systematic review](https://pmc.ncbi.nlm.nih.gov/articles/PMC7651899/). *Journal of the American Medical Informatics Association*, 24(2), 423–431.

### AI output and the cost of review

A 2025 randomized study by METR examined 16 experienced open-source developers completing 246 tasks in familiar repositories. In that setting, developers using the AI tools tested took 19% longer on average, even though they had expected the tools to make them faster. The result is specific to the participants, tools, tasks, and codebases in the study; it is not a universal estimate of AI productivity.

The study is relevant because producing code is only one part of completing a software task. Reviewing and correcting generated work can offset the time saved during generation. The same distinction—between output produced and work successfully completed—needs to be examined in other kinds of AI-assisted work rather than assumed to transfer unchanged.

Reference: Becker, J., Rush, N., Barnes, B. & Rein, D. (2025). [Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity](https://arxiv.org/abs/2507.09089). See also [METR's study page and materials](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/).

### Verification, validation, and accountable AI practice

The US National Institute of Standards and Technology's AI Risk Management Framework and AI Resource Center treat testing, evaluation, verification, and validation (TEVV) as important parts of AI risk management. This is standards and practice guidance, rather than experimental evidence that any particular checklist or workflow succeeds.

It reinforces a practical distinction: a system's claim about its performance is not a substitute for testing the relevant behavior and retaining enough information to understand what was checked.

References:
- NIST, [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework).
- NIST, [AI Resource Center: testing, evaluation, verification, and validation](https://airc.nist.gov/).

## 2. A related problem in AI-assisted work

Taken together, these sources motivate a general concern: **the effort needed to generate output can be lower than the effort needed to establish whether that output is complete and correct.** If the work is spread across repositories, temporary archives, generated reports, and confident status claims, the person responsible for accepting it may have to do substantial investigative work.

Several distinct failure modes can contribute:

- **Deliverable substitution:** descriptions, plans, manifests, or reports are produced in place of the requested artifact.
- **Destination ambiguity:** an artifact exists locally or in a temporary location but has not reached the specified destination.
- **Verification ambiguity:** existence is treated as proof of completeness, integrity, functionality, or correctness.
- **Status inflation:** an attempt or generation step is described as if delivery and verification were complete.
- **Verification overhead:** duplicate documentation and scattered evidence make it harder to establish what is real, missing, or tested.

These are the mechanisms this skill targets. The cited research motivates the concern; it does not establish that all of these failure modes occur together, or that one procedure will eliminate them.

## 3. Independent observations and related work

I encountered related problems in AI-assisted work and tried to address them through my own framework and experiments. This work is a separate line of inquiry: it should be read alongside external research, not as a substitute for it.

Three existing pieces of work are especially relevant:

- [The Intern Who Never Sleeps](https://www.memoryprism.com/positions/ai-intern-monkeys) examines the asymmetry between rapid generation and the human capacity to review it. Its concern is that output can accumulate faster than a person can meaningfully inspect it.
- [AEL and AI](https://www.memoryprism.com/positions/ael-and-ai) considers the gap between a stated objective and the consequences of an AI system's behavior.
- [AEL Runtime Accountability — V1](https://www.memoryprism.com/readings/ael-runtime-accountability) explores making errors legible, cheap to locate, reversible, and attributable before sunk costs accumulate.

These works provide the user's own conceptual framing and proposed responses. The external research and this work converge on related concerns, but they are not interchangeable bodies of evidence and neither automatically validates the other.

### A concrete test case

During a Faking Vision CCTV reconstruction task, the requested outputs included three FV packets with populated snapshot folders, a reconstructed video, and merged object and temporal data. The user reported that numerous supporting documents had been produced while the requested artifacts were missing from the intended GitHub destination or existed only in a local archive.

That experience illustrates deliverable substitution and destination ambiguity. It is a case for testing a general capability, not the definition of the problem and not the sole justification for creating this skill.

Related example: [Faking Vision — CCTV Snapshot TD Reconstruction Experiment](https://github.com/memoryprismv1/faking-vision/tree/main/PACKETS/examples/videos/CCTV_Snapshot_TD_Reconstruction_Experiment).

## 4. The proposed intervention

Verification Integrity turns the general concern into a compact operational rule:

1. **Deliver the requested artifacts themselves.** Do not replace them with descriptions of the work.
2. **Treat the destination as part of the deliverable.** Check that the outputs reached the location the user specified.
3. **Inspect the actual outputs.** Check the properties that matter to the task, rather than relying only on status claims or supporting documentation.
4. **State the verification boundary.** Distinguish attempted, generated, delivered, inspected, tested, and verified work.
5. **Keep the evidence proportionate.** Retain enough evidence to establish what happened, but do not create paperwork that increases the verification burden.
6. **Stop when done.** Do not add files or process machinery that the task does not need.

The goal is not to eliminate documentation. Documentation is valuable when it helps people trace, understand, or reproduce important work. The goal is to avoid documentation that merely looks like evidence or makes the actual deliverables harder to find.

## 5. Relationship to Task Integrity

[Task Integrity](../task-integrity/README.md) already covers scope, coverage, provenance, honest completion claims, and traceable correction. Verification Integrity is narrower and complementary: it focuses on the artifact, its destination, the properties actually checked, and the cost imposed on the person verifying it.

A substantial task may need both. Neither requires a separate report or ledger for every small task, and the two skills should not generate duplicate machinery.

## 6. Evaluation

The skill should be tested across task types, not judged by whether its own instructions sound persuasive. Useful measures include:

- whether the requested artifacts are present at the intended destination;
- whether omissions and incomplete outputs are detected;
- whether claims distinguish delivery from inspection and testing;
- whether checks cover the relevant properties of the actual outputs;
- whether explicit file and documentation constraints are respected;
- how much effort a person needs to establish what was completed and what remains unresolved;
- whether the process avoids unnecessary artifacts without losing evidence needed for accountability.

Compare results with and without the skill on representative tasks. Track failures and human verification effort, not only the AI's self-reported compliance.

## 7. Evidence boundary

**Supported by external research and guidance:** verification of automation can be cognitively demanding; automation bias is associated with verification complexity in the reviewed literature; AI-assisted output can fail to reduce total task time in at least some real-world coding settings; and established AI risk-management practice treats testing and verification as important activities.

**Contributed by the user's independent work:** the AEL framing, the linked analyses of generation/review asymmetry and runtime accountability, and the observed CCTV reconstruction case.

**Proposed here, not yet validated:** this exact skill's procedures will reduce omissions, improve delivery reliability, or lower the human cost of verification. Those claims require direct evaluation.
