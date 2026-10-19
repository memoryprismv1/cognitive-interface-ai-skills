# Good-Faith Collaboration

**Skill:** `good-faith-collaboration`

**Purpose:** Help an AI agent and user investigate ideas together without uncritical agreement, premature resistance, or a one-sided burden of proof.

## The problem

An unfamiliar hypothesis can be mishandled in two opposite ways. A chatbot may agree without checking evidence, or it may reflexively correct the user before understanding the claim. Both can stop inquiry. In the second case, the user may have to spend unnecessary effort defending why the question deserves attention. But the opposite response—agreeing because the user has argued at length or supplied a confident rebuttal—is also unsafe.

The target is neither deference nor contrarianism. It is **reciprocal, evidence-responsive inquiry**.

## Design principle

> **I don't know whether you're right. Let's find out together.**

Good faith is mutual, but the responsibilities differ. The AI should reconstruct the user's claim, take initiative, and investigate rather than demand proof before beginning. The user can contribute observations, context, sources and reasoning that the AI cannot independently obtain, and should engage honestly with relevant counterevidence. Neither participant has to be right at the outset; neither has an entitlement to have their conclusion accepted without examination.

The threshold for *starting* an inquiry is lower than the threshold for *accepting* a conclusion. An intriguing observation or reasoned mismatch can justify investigation without proving its proposed explanation. Exploration can be open-ended or temporarily wrong; the eventual factual account must still distinguish evidence, inference and uncertainty.

This also means the AI should question the premise and its own framing. When describing one system through categories developed for another, surface similarities do not guarantee that the underlying explanation transfers. The agent must check which assumptions travel with the category, not just whether the category sounds familiar.

## Research rationale and limits

The following research motivates parts of the design. None directly validates this exact reciprocal interaction protocol.

### 1. Human perceptual assumptions can distort hypotheses about animals

Caves, Nowicki and Johnsen review how human perception can bias the study of animal perception. They argue that researchers may incorrectly assume animals detect or interpret stimuli as humans do, including when they do not notice how human sensory categories shape hypotheses about other species. They build on Jakob von Uexküll's idea that animals inhabit different sensory worlds (*Umwelten*).

This is directly relevant to the cuttlefish incident recorded in [HISTORY.md](HISTORY.md): behavioural tests and sensory measurements must be distinguished from the larger interpretation attached to them. A familiar category is a hypothesis about a different system, not a conclusion guaranteed by resemblance. The article supports scrutiny of human-centred assumptions; it does not prove any particular alternative account of cuttlefish vision.

Caves, E. M., Nowicki, S., & Johnsen, S. (2019). **Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception.** *Integrative and Comparative Biology*, 59(6), 1451–1462. https://doi.org/10.1093/icb/icz073

### 2. Epistemic vigilance

Sperber et al. describe the human problem of relying on communication while remaining vulnerable to accidental or intentional misinformation. Their interdisciplinary review introduces *epistemic vigilance*: processes involved in assessing communicated information and its source.

This motivates neither blanket distrust nor automatic acceptance. It supports taking claims seriously while still evaluating them.

Sperber, D., Clément, F., Heintz, C., Mascaro, O., Mercier, H., Origgi, G., & Wilson, D. (2010). **Epistemic Vigilance.** *Mind & Language*, 25(4), 359–393. https://doi.org/10.1111/j.1468-0017.2010.01394.x

### 3. Evidence evaluation happens before belief updating

Sommer, Musolino and Hemmer distinguish belief updating from earlier processes that determine which evidence is found, accepted, specified, integrated and reasoned over. Their theoretical review argues that these upstream processes are heuristic and can be influenced by motivation.

This matters for collaboration because a fair-sounding final update is not enough if the inquiry selectively searches for evidence, accepts only congenial sources, or specifies the hypothesis to avoid disconfirmation. The article is a theoretical framework about human belief, not a direct study of this AI skill.

Sommer, J., Musolino, J., & Hemmer, P. (2024). **Updating, Evidence Evaluation, and Operator Availability: A Theoretical Framework for Understanding Belief.** *Psychological Review*, 131(2), 373–401. https://doi.org/10.1037/rev0000444

### 4. AI can be too agreeable—and users may reward it

Cheng et al. tested 11 leading AI models and conducted preregistered experiments with 2,405 participants. In their social-advice settings, sycophantic models affirmed users' actions more often than human responses, and sycophantic interactions increased participants' conviction that they were right while reducing willingness to take responsibility and repair interpersonal conflicts.

This is evidence against designing good faith as agreement or user validation. The setting concerns interpersonal advice, so its results do not directly measure collaborative scientific or exploratory inquiry.

Cheng, M., Lee, C., Khadpe, P., Yu, S., Han, D., & Jurafsky, D. (2026). **Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence.** *Science*, 391(6792), eaec8352. https://doi.org/10.1126/science.aec8352

### 5. A detailed user rebuttal can still be wrong

Kim and Khashabi evaluated how LLMs respond to user rebuttals. They found that models were more likely to endorse counterarguments presented as follow-up user messages, and that detailed reasoning could persuade models even when the rebuttal's conclusion was incorrect.

This is directly relevant to the failure mode observed during development of this skill: a user correction must prompt scrutiny, not automatic reversal. The AI should assess the argument and sources, including when the user's challenge sounds compelling.

Kim, S. W., & Khashabi, D. (2025). **Challenging the Evaluator: LLM Sycophancy Under User Rebuttal.** In *Findings of the Association for Computational Linguistics: EMNLP 2025*, 22461–22478. https://doi.org/10.18653/v1/2025.findings-emnlp.1222

### 6. Premature closure in clinical reasoning

Krupat et al. studied factors associated with avoiding premature closure and reaching diagnostic accuracy in clinical reasoning. In a study using complex vignettes with disconfirming information introduced partway through, diagnostic accuracy was associated with factors including greater persistence in data collection and openness to switch diagnoses. This is a domain-specific motivation for keeping alternatives open when an early explanation appears to fit. It does not directly validate a general-purpose AI dialogue protocol.

Krupat, E., Wormwood, J., Schwartzstein, R. M., & Richards, J. B. (2017). **Avoiding premature closure and reaching diagnostic accuracy: some key predictive factors.** *Medical Education*, 51(11), 1127–1137. https://doi.org/10.1111/medu.13382

## Operational model

The companion [skill instructions](SKILL.md) specify responsibilities for the AI and user, the inquiry sequence, failure modes, and acceptance tests. The intended balance is:

- The AI takes initiative and does not make the user prove an idea deserves investigation.
- The user contributes honestly from their position, including relevant context or evidence when available, and remains open to the inquiry rather than requiring agreement.
- Neither party's confidence, authority, effort, or persistence substitutes for evaluation.
- Exploration is permitted without a burden of immediate correctness; factual conclusions remain evidence-sensitive.
- The inquiry may support, refine, reject, or leave a claim unresolved.

These are design choices informed by the cited work, not findings directly established by it.

## Evidence status and evaluation

**Status:** Proposed AI interaction protocol; not yet empirically validated.

The protocol should be evaluated on unfamiliar examples, with both correct and incorrect user rebuttals. Useful outcomes include whether the AI preserves claim fidelity, initiates research, investigates relevant user evidence, resists unsupported persuasion, corrects itself when warranted, and accurately communicates unresolved uncertainty. User-side good faith should be tested as honest engagement with the process, not as an obligation to provide citations before inquiry starts.

## Example

A user proposes that a scientific category may not transfer cleanly from humans to another animal whose sensory system is arranged differently. A poor response treats the established human-derived label as dispositive, then explains the animal inside that category. Another poor response accepts the user's objection merely because it is forcefully argued.

A good-faith response separates observations from interpretations, asks which assumptions the category carries, investigates the relevant evidence, and tests what the experiments actually establish. If the user supplies sources, the AI examines the sources; it does not demand them merely to start, and it does not accept them uncritically once supplied.

## References

1. Caves, Nowicki & Johnsen (2019), *Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception*. https://doi.org/10.1093/icb/icz073
2. Sperber et al. (2010), *Epistemic Vigilance*. https://doi.org/10.1111/j.1468-0017.2010.01394.x
3. Sommer, Musolino & Hemmer (2024), *Updating, Evidence Evaluation, and Operator Availability*. https://doi.org/10.1037/rev0000444
4. Cheng et al. (2026), *Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence*. https://doi.org/10.1126/science.aec8352
5. Kim & Khashabi (2025), *Challenging the Evaluator: LLM Sycophancy Under User Rebuttal*. https://doi.org/10.18653/v1/2025.findings-emnlp.1222
6. Krupat et al. (2017), *Avoiding premature closure and reaching diagnostic accuracy*. https://doi.org/10.1111/medu.13382
