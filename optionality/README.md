# Optionality

**Skill:** `optionality`

**Status:** Version 1; research-informed design proposal, not yet empirically validated.

**Purpose:** Help people who value optionality keep meaningful possibilities available across thinking, software, education, planning, and everyday problem-solving.

> **Governing principle: Do not collapse a possibility space prematurely.**

Optionality is not simply producing multiple answers. It is the ability to identify and develop materially different possibilities without requiring the user to evaluate or choose all of them. The user may want alternatives available even when they intend to continue with their original choice.

## The problem

Current AI interactions often converge too early. A model identifies one object, interpretation, or candidate solution and makes it the centre of subsequent reasoning. It then extends one line of thought rather than maintaining independent possibilities. This can produce:

- **Object fixation:** the first identified object or framing dominates the investigation.
- **Path fixation:** one reasoning trajectory becomes the default, even when other routes may be useful.
- **Possibility collapse:** superficially different outputs conceal a shared assumption or underlying approach.
- **Human correction overhead:** the user must repeatedly redirect the AI, challenge its framing, and recover alternatives the AI did not consider.

Generating a larger answer or listing several options does not necessarily fix these problems. The alternatives may be cosmetic variations of the same idea, or may be dumped on the user without being explored.

Optionality is intended for people who actively want possibilities available. It is not a universal interaction style. The skill is explicitly activated by the user or suggested through a restrained, contextual nudge when useful alternatives seem likely to exist.

## Design principles

1. **User-valued, not compulsory.** Optionality is available to people who want it. It does not silently become the default for everyone.
2. **Nudge on potential value, not the mere existence of choices.** The AI may say that other meaningful routes seem possible and ask whether the user wants to explore them. A nudge does not activate the skill.
3. **Distinction before quantity.** Alternatives should differ in assumptions, mechanisms, perspectives, constraints, scale, or route—not just wording.
4. **Develop and preserve.** Explore useful branches enough to reveal their implications, and keep viable alternatives available without forcing a decision.
5. **User agency.** The AI explores; the user chooses whether to activate, continue, switch, combine, defer, or stop.
6. **Restraint.** Do not turn every exchange into brainstorming or make the user manage unnecessary branches.

## Research rationale

The research is relevant to different parts of the design. No single paper establishes the complete skill. Evidence about human choice and agency, developmental learning, LLM reasoning, and human–AI interaction must remain distinct.

### A. Human choice, perceived control, and agency

**1. The inherent reward of choice**

Leotti, L. A., & Delgado, M. R. (2011). *The Inherent Reward of Choice.* **Psychological Science, 22**(10), 1310–1318. https://doi.org/10.1177/0956797611417005

An fMRI study of anticipating choice. It reported preference for cues that allowed choice and activity in corticostriatal reward-related regions. This supports the idea that the opportunity to choose can have value before an outcome is selected.

**2. Perceived freedom and option availability**

Rens, N., Bode, S., & Cunnington, R. (2018). *Perceived Freedom of Choice Is Associated with Neural Encoding of Option Availability.* **NeuroImage, 177**, 59–67. https://doi.org/10.1016/j.neuroimage.2018.04.070

Participants reported greater freedom when alternatives remained available, including when they continued with their original choice. Neural encoding of option availability was associated with perceived freedom. This is particularly relevant to the distinction between having an alternative available and actually choosing it.

**3. Freedom of action selection, effort, and agency**

Barlas, Z., Hockley, W. E., & Obhi, S. S. (2017). *The Effects of Freedom of Choice in Action Selection on Perceived Mental Effort and the Sense of Agency.* **Acta Psychologica, 180**, 122–129.

This behavioural study varied the number of action alternatives and examined subjective effort and agency. Its results suggest that choice, agency, and effort can relate in non-identical ways. It is not an fMRI study and does not establish that more options always reduce effort.

**4. Control and stress regulation**

Meine, L. E., et al. (2021). *Don't Stress, It's Under Control: Neural Correlates of Stressor Controllability in Humans.* **NeuroImage, 245**, 118701. https://doi.org/10.1016/j.neuroimage.2021.118701

A human neuroimaging study of controllable and uncontrollable aversive stimulation. It supports the relevance of perceived control to stress regulation, but controllability of a stimulus is not identical to the availability of alternative learning or problem-solving routes.

### B. Choice overload and cognitive cost

**5. Neural signatures of choice overload**

Reutskaja, E., et al. (2018). *Choice Overload Reduces Neural Signatures of Choice Set Value in Dorsal Striatum and Anterior Cingulate Cortex.* **Nature Human Behaviour, 2**, 925–935. https://doi.org/10.1038/s41562-018-0440-2

An fMRI study comparing choice sets of different sizes. Neural responses showed an inverted-U pattern during active choice; the pattern was absent during browsing. This is an important reason not to equate availability with mandatory evaluation or selection.

**Evidence implication:** Optionality should make alternatives available without requiring users to inspect and rank every alternative. More choices are not automatically better.

### C. Development, learning, and continuity

**6. Exploration and cognitive flexibility across development**

Gopnik, A., et al. (2017). *Changes in Cognitive Flexibility and Hypothesis Search Across Human Life History from Childhood to Adolescence to Adulthood.* **Proceedings of the National Academy of Sciences.** https://www.pnas.org/doi/10.1073/pnas.1620748114

This research compares hypothesis search across developmental stages. It suggests that exploratory behaviour and the use of prior knowledge change during development. It does not show that every child is naturally more flexible, or that childhood exposure to optionality produces more flexible adults.

**7. Stability of students' learning-environment preferences**

Könings, K. D., Brand-Gruwel, S., & Elen, J. (2012). *Effects of a School Reform on Longitudinal Stability of Students' Preferences with Regard to Education.* **British Journal of Educational Psychology, 82**(3), 512–532. https://doi.org/10.1111/j.2044-8279.2011.02044.x

A longitudinal study of secondary-school students that found stability in many measured learning-environment preferences over repeated measurements, alongside changes in some preferences. This supports taking learner preferences seriously without treating them as immutable traits.

**8. Multiple external representations in STEM**

Rexigel, E., Kuhn, J., Becker, S., et al. (2024). *The More the Better? A Systematic Review and Meta-Analysis of the Benefits of More than Two External Representations in STEM Education.* **Educational Psychology Review, 36**, 124. https://doi.org/10.1007/s10648-024-09958-y

A review and meta-analysis reporting benefits for learning performance and cognitive load under the studied conditions. Multiple representations are not the same as multiple delivery modalities, and their benefits depend on how they are designed and supported.

**9. Learning-style matching caution**

Clinton-Lisell, V., & Litzinger, C. (2024). *Is It Really a Neuromyth? A Meta-Analysis of the Learning Styles Matching Hypothesis.* **Frontiers in Psychology, 15**, 1428732. https://doi.org/10.3389/fpsyg.2024.1428732

This review reports a small overall effect but substantial variability and limited support for the crossover interactions needed to establish reliable learning-style matching. Optionality must not classify a learner permanently as visual, auditory, reading-oriented, or kinesthetic.

**Developmental research gap:** Existing research gives reasons to preserve learner choice and make different representations available. It does not yet establish that deliberately exposing children to multiple learning routes causes them to become more flexible adult learners. That remains a hypothesis for longitudinal research.

### D. AI reasoning, anchoring, and diversity

**10. Tree of Thoughts: branching, evaluation, and backtracking**

Yao, S., Yu, D., Zhao, J., Shafran, I., Griffiths, T. L., Cao, Y., & Narasimhan, K. (2023). *Tree of Thoughts: Deliberate Problem Solving with Large Language Models.* **NeurIPS 2023.** https://arxiv.org/abs/2305.10601

Introduces search over coherent intermediate thoughts, including branching, evaluation, lookahead, and backtracking. In the Game of 24 experiment, GPT-4 with ordinary Chain-of-Thought solved 4% of tasks, compared with 74% using Tree of Thoughts. This demonstrates the value of structured exploration on selected search-heavy tasks; it does not establish that branching alone prevents shared framing or object fixation.

**11. Confirmation bias during hypothesis search**

Jhaveri, A. R., Chen, A. G.-X., Sucholutsky, I., & Choi, E. (2026). *Failing to Falsify: Evaluating and Mitigating Confirmation Bias in Language Models.* https://arxiv.org/abs/2604.02485

Across eleven LLMs, the authors adapted a rule-discovery task and found that models often proposed examples that confirmed rather than challenged their current hypothesis. A prompt intervention encouraging counterexamples improved average rule-discovery rates from 42% to 56%. This supports treating the first hypothesis as a candidate to test, not as the organising truth. The reported evaluation is specific to the tested tasks.

**12. Anchoring in LLM judgements**

Lou, J., & Sun, Y. (2025; journal volume dated 2026). *Anchoring Bias in Large Language Models: An Experimental Study.* **Journal of Computational Social Science, 9**, article 11. https://doi.org/10.1007/s42001-025-00435-2

An experimental study of the influence of initial information on later LLM judgements. The authors report susceptibility to biased hints and find that collecting information from multiple angles is more useful than relying on simple Chain-of-Thought or reflection interventions. This is evidence about anchoring in the tested setup, not proof that every conversational model response is anchored.

**13. Multi-answer reinforcement learning and mode concentration**

Puri, I., Damani, M., Shenfeld, I., Ghassemi, M., Andreas, J., & Kim, Y. (2026). *Escaping the Mode: Multi-Answer Reinforcement Learning in LMs.* **Proceedings of the 43rd International Conference on Machine Learning, PMLR 306**, 100127–100146. https://proceedings.mlr.press/v306/puri26a.html

Studies how post-training can concentrate a model's answer distribution around one dominant response, even when a task admits multiple valid answers or uncertainty. The proposed multi-answer reinforcement-learning approach trains models to produce multiple plausible candidates with confidence estimates. This is a training-level intervention, not a user-facing skill.

**14. Distribution matching for diverse reasoning**

Li, X., et al. (2026). *Beyond Mode Collapse: Distribution Matching for Diverse Reasoning.* **Proceedings of the 43rd International Conference on Machine Learning, PMLR 306**, 67829–67847. https://proceedings.mlr.press/v306/li26cc.html

The authors attribute reduced diversity in some on-policy reinforcement-learning methods to reverse-KL mode-seeking behaviour and propose distribution matching to preserve multiple high-reward reasoning trajectories. The work concerns training objectives and benchmarked reasoning tasks; it does not imply that every deployed model or every single response necessarily suffers from this specific mechanism.

**15. Diversity collapse associated with structured prompting formats**

Yun, L., An, C., Wang, Z., Peng, L., & Shang, J. (2025). *The Price of Format: Diversity Collapse in LLMs.* **Findings of EMNLP 2025**, 15454–15468. https://doi.org/10.18653/v1/2025.findings-emnlp.836

This work reports that structured instruction templates can constrain semantic diversity on open-ended generation tasks, with the effect persisting under higher-temperature sampling. It suggests that interaction format can influence output diversity; it does not show that all structured prompts suppress useful reasoning.

**16. Human–AI design fixation**

Wadinambiarachchi, S., Kelly, R. M., Pareek, S., Zhou, Q., & Velloso, E. (2024). *The Effects of Generative AI on Design Fixation and Divergent Thinking.* **CHI 2024**, article 380. https://doi.org/10.1145/3613904.3642919

In a between-participants visual ideation experiment (N=60), participants using an AI image generator showed greater fixation on an initial example; the AI-supported group produced fewer ideas with less variety and lower originality than the baseline. This directly concerns human–AI co-creation in a visual design task, not every form of text-based AI assistance.

**17. Human–AI homogenisation**

de Rooij, A. (2026). *Does Generative AI Make Us Think Alike? A Systematic Review and Meta-analysis of Homogenisation Effects in Human–AI Co-creation.* **Behaviour & Information Technology.** https://doi.org/10.1080/0144929X.2026.2726451

A systematic review and three-level meta-analysis of 19 studies and 61 effect sizes. It reports a small positive pooled homogenisation effect, with substantial heterogeneity. The authors distinguish collective similarity of outputs from a decline in any one person's creativity. This supports careful evaluation of diversity across people and outputs, not a blanket claim that AI always makes users think alike.

**18. Diverse output distributions**

Bellemare-Pepin, A., et al. (2026). *Divergent Creativity in Humans and Large Language Models.* **Scientific Reports, 16**, article 1279. https://www.nature.com/articles/s41598-025-25157-3

Compares semantic diversity in human and LLM responses. The work is relevant to the difference between producing many responses and covering a wider range of ideas. Its findings should be interpreted in relation to the study's divergent-thinking tasks, not as a universal measure of reasoning quality.

These papers describe different levels of the problem: human anchoring and fixation, model output distributions, training-time mode collapse, inference-time branching, and human–AI interaction effects. They should not be collapsed into one explanation or treated as interchangeable evidence.

## Proposed evaluation

Compare identical tasks with Optionality enabled and disabled. Include domains that differ substantially:

- Software architecture: several viable designs with different trade-offs.
- Research: competing explanations for an observation.
- Everyday task management: different routes around a practical obstacle.
- Education: alternative ways to approach the same learning objective.

Measure:
- Number of genuinely distinct, relevant possibilities.
- Similarity between alternatives and whether they share a hidden assumption.
- Whether the initial object or hypothesis dominates later reasoning.
- Whether branches are developed independently before comparison.
- Whether alternatives remain available without forcing a decision.
- Nudge precision: useful invitations versus unnecessary interruptions.
- User correction overhead: how much redirection is needed to escape the AI's initial framing.
- Unnecessary expansion when a direct answer is sufficient.

Include cases where no nudge should be made and cases where a nudge would be useful but the alternatives are uncertain. Evaluate the skill against user preference, not maximum output diversity.

## Evidence boundary and open questions

**Supported by research:** Choice availability can have psychological and neural significance; active evaluation of large choice sets can impose costs; cognitive exploration changes with development; multiple representations can support learning under some conditions; AI-generated examples can contribute to fixation in some tasks; LLM reasoning methods can explicitly branch.

**Not established:** That this Optionality skill reliably reduces cognitive load, improves general creativity or cognitive flexibility, reduces correction overhead across domains, or creates more flexible adult learners through childhood use.

These are testable engineering and developmental hypotheses, not established outcomes.

## Status

**Version:** 1.0 — initial operational design.

**Core principle:**

> Make meaningful possibilities available. Do not make the user do unnecessary work to discover them, evaluate all of them, or escape the AI's first idea.
