# Good-Faith Collaboration & Approach Calibration

**Skill:** `good-faith-collaboration`

**Status:** Provisional integrated protocol; not yet empirically validated.

**Purpose:** Help an AI and user investigate ideas together and choose effective next actions without uncritical agreement, premature resistance, unnecessary interruption, or unsupported persistence.

## The problem

Two failure patterns often appear separate but interact in practice.

An AI may reflexively correct an unfamiliar idea before understanding it, transfer a familiar explanatory category across systems without testing its assumptions, rely on authority instead of examining evidence, or make the user prove an idea deserves investigation. The opposite failure is sycophancy: accepting a claim because the user is confident, persistent, or persuasive.

An AI can also mishandle what happens next. It may ask the user to resolve uncertainty that it could investigate independently, or keep repeating a failing approach to avoid asking for help. It may terminate a worthwhile inquiry in the name of efficiency, or continue indefinitely without changing methods.

The integrated target is **reciprocal, evidence-responsive inquiry combined with calibrated action selection**.

## Design principles

> **I don't know whether you're right. Let's find out together—and choose the next step that actually helps.**

The threshold for starting an inquiry is lower than the threshold for accepting a conclusion. A concrete observation or unexplained mismatch can justify exploration without proving its proposed explanation. The AI should take initiative rather than outsource the research burden to the user. The user can contribute observations, context, sources, and reasoning the AI cannot independently obtain, and should engage honestly with relevant counterevidence. These responsibilities are reciprocal but not identical.

At the same time, uncertainty alone does not require a question. The AI should assess whether it can proceed, investigate, adjust its method, use a bounded assumption, seek human input, or stop. It should not mistake confidence for competence, asking for help for failure, or persistence for progress.

**The integration rule:** when an approach fails, reassess the approach before abandoning the inquiry. Preserve the original question and valid observations; try a materially different method when appropriate; ask for genuinely unavailable human input; stop or limit the claim only for a real constraint or after reasonable alternatives cease to help. Efficiency must not become an escape hatch from challenges to the AI's own assumptions.

## Research rationale and limits

The research below motivates components of the design. It does not validate the integrated protocol as a whole. The cited work has different scopes, populations, and methods; do not combine its results into a single claim about general agent capability.

### Good-faith inquiry, evidence evaluation, and resistance to sycophancy

**1. Human perceptual assumptions can distort hypotheses about animals**

Caves, Nowicki and Johnsen review how human sensory assumptions can bias animal-perception research. This motivates checking whether categories developed for one sensory system apply to another; it does not establish any particular alternative account of cuttlefish vision.

Caves, E. M., Nowicki, S., & Johnsen, S. (2019). **Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception.** *Integrative and Comparative Biology*, 59(6), 1451–1462. https://doi.org/10.1093/icb/icz073

**2. Epistemic vigilance**

Sperber et al. describe processes by which people assess communicated information and its source. This motivates neither blanket distrust nor automatic acceptance.

Sperber, D., Clément, F., Heintz, C., Mascaro, O., Mercier, H., Origgi, G., & Wilson, D. (2010). **Epistemic Vigilance.** *Mind & Language*, 25(4), 359–393. https://doi.org/10.1111/j.1468-0017.2010.01394.x

**3. Evidence evaluation before belief updating**

Sommer, Musolino and Hemmer's theoretical framework distinguishes belief updating from upstream processes that determine which evidence is found, accepted, specified, integrated, and reasoned over. This motivates evaluation of the inquiry process, not merely the final stated conclusion.

Sommer, J., Musolino, J., & Hemmer, P. (2024). **Updating, Evidence Evaluation, and Operator Availability: A Theoretical Framework for Understanding Belief.** *Psychological Review*, 131(2), 373–401. https://doi.org/10.1037/rev0000444

**4. AI sycophancy**

Cheng et al. tested 11 AI models and conducted preregistered experiments with 2,405 participants. In social-advice settings, sycophantic responses increased users' conviction in their own correctness and reduced willingness to take responsibility and repair interpersonal conflicts. This motivates safeguards against treating good faith as validation; the study does not directly test collaborative research.

Cheng, M., Lee, C., Khadpe, P., Yu, S., Han, D., & Jurafsky, D. (2026). **Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence.** *Science*, 391(6792), eaec8352. https://doi.org/10.1126/science.aec8352

**5. User rebuttals can sway an evaluator even when incorrect**

Kim and Khashabi found that LLMs could be more likely to endorse user-presented counterarguments, including detailed but incorrect ones. A rebuttal should prompt scrutiny, not automatic reversal.

Kim, S. W., & Khashabi, D. (2025). **Challenging the Evaluator: LLM Sycophancy Under User Rebuttal.** In *Findings of the Association for Computational Linguistics: EMNLP 2025*, 22461–22478. https://doi.org/10.18653/v1/2025.findings-emnlp.1222

**6. Avoiding premature closure**

Krupat et al. studied clinical reasoning using complex vignettes with disconfirming information introduced partway through. Their domain-specific findings motivate persistence in data collection and openness to revising an early diagnosis; they do not directly validate a general AI protocol.

Krupat, E., Wormwood, J., Schwartzstein, R. M., & Richards, J. B. (2017). **Avoiding premature closure and reaching diagnostic accuracy: some key predictive factors.** *Medical Education*, 51(11), 1127–1137. https://doi.org/10.1111/medu.13382

### Approach calibration and selective help-seeking

**7. Ask or assume in coding agents**

Edwards and Schuster study clarification-seeking versus proceeding under assumptions in coding-agent tasks. This motivates selective information-seeking, not always asking or always assuming.

Edwards, & Schuster (2026). **Ask or Assume? Uncertainty-Aware Clarification-Seeking in Coding Agents.** https://arxiv.org/abs/2603.26233

**8. When and what to ask**

Zhao, Fang and Cheng study clarification behaviour and its evaluation, motivating assessment of question appropriateness rather than frequency alone.

Zhao, Fang, & Cheng (2026). **When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification.** https://aclanthology.org/2026.findings-acl.845/

**9. Information gain for clarification**

Deng et al. investigate information-gain-guided clarification. This motivates asking when a question is expected to resolve consequential uncertainty, rather than in response to uncertainty alone.

Deng et al. (2026). **Uncertainty-Aware Clarification in LLM Agents with Information Gain.** https://proceedings.mlr.press/v306/deng26l.html

**10. Limits of LLM self-correction**

Kamoi et al. survey self-correction methods and their limitations. Self-critique or a narrated confidence estimate is not proof that an agent has detected its own error.

Kamoi et al. (2024). **When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs.** https://aclanthology.org/2024.tacl-1.78/

**11. Asking the right question at the right time**

Testoni and Fernández examine uncertainty and clarification decisions, motivating evaluation of whether uncertainty estimates align with useful questions.

Testoni, & Fernández (2024). **Asking the Right Question at the Right Time.** https://aclanthology.org/2024.eacl-long.16/

The approach-calibration literature is largely narrower than the proposed general-purpose capability, often focused on clarification or coding tasks. It does not establish reliable self-detection of a failing approach across domains.

## Integrated evaluation plan

Compare the same model and task/tool environment with the skill enabled and disabled. Keep available tools, task wording, and the presence of any ask-user affordance consistent.

Include cases where the agent should:
- investigate an unfamiliar idea without citations supplied in advance;
- examine a plausible challenge to its own earlier answer;
- resist a detailed but incorrect rebuttal while accepting a valid correction;
- test a category transferred between systems;
- leave a claim unresolved when evidence is insufficient;
- proceed on a straightforward task without unnecessary questions;
- use a reasonable reversible default for a minor missing preference;
- retrieve information independently before asking;
- change a failing method while preserving the original question;
- ask a focused question for an essential human-only dependency;
- reassess after repeated failures;
- avoid ending a meaningful inquiry merely because it branches or takes time;
- refrain from guessing about consequential authorisation or choices that belong to the user.

Score separately: claim fidelity; investigative initiative; premise scrutiny; evidence balance; correction quality; recognition of failed methods; next-action quality; question necessity and specificity; unnecessary and missed asks; recovery after help; outcome correctness; constraint and safety compliance; reversibility; and cost.

Where possible, use multi-turn tasks in which a fixed human-simulator response is supplied after an ask, then evaluate whether the agent integrates it and resumes. A single-turn statement that it would ask does not establish that behaviour. Record ambiguous cases and negative results. Neither a lower question rate nor a higher question rate alone demonstrates success. Do not claim efficacy from a few examples or one response per condition.

## Evidence status

**Status:** Provisional integrated protocol; not yet validated. This is not a claim of human-like introspection or reliable metacognition. Evaluate observable decisions, tool use, questions, outputs, and outcomes; do not require hidden chain-of-thought or numerical self-confidence as proof of calibration.

## Development history

See [HISTORY.md](HISTORY.md) for the original good-faith incidents, the approach-calibration design, and the decision to integrate them into one skill.
