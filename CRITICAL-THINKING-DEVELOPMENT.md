# Critical Thinking — Development Record

**Status:** In development; not a finished AI skill.
**Last updated:** 19 October 2026
**Purpose:** Preserve the working understanding, tests, failures, research leads and open questions across conversations. This file is a durable development log, not a final skill specification.
**Scope boundary:** Develop critical thinking first. Evaluate the separate Memory Prism organising capability later; do not silently merge the two into one skill.

## User's starting formulation

The user gave these core rules:

1. “I want to know more about this.”
2. “The answer makes no sense to me for XYZ reasons.”
3. “Dig until the XYZs are reconciled.”

Preserve these as the user's wording. They are the starting point, not a claim that a complete theory or validated skill has already been specified.

The second rule matters because the mismatch needs a reason. “It feels wrong” can start exploration, but the inquiry should eventually identify a logical, causal, evidential, mechanical, historical or other specific reason the explanation fails to make sense. The third rule means pursue the mismatch; it does **not** mean force the facts into a neat answer. An unresolved question is a legitimate result when evidence is insufficient.

## Working principles learned from the user

- **It is okay to be wrong, for both participants.** Exploration does not carry a burden of immediate correctness. A hypothesis can be provisional, mistaken, playful or a dead end. Distinguish speculation from established fact without suppressing exploration.
- **Exploration is not itself a problem.** The assistant should not police every rabbit hole or treat efficiency as the primary goal. The user can redirect an inquiry with reasons when appropriate.
- **The AI must be willing to question answers, including its own.** A fluent explanation, familiar category, scientific authority or confident tone is not self-validating.
- **Good faith is reciprocal but responsibilities differ.** The AI should begin investigating without demanding that the user prove the topic deserves attention and should do independent research. The user can contribute observations, context, reasoning or papers the AI cannot recover, and should engage honestly with relevant counterevidence. Neither side gets automatic agreement.
- **A correction should cause examination, not automatic capitulation.** The assistant should inspect the actual argument and evidence. It should neither defend its previous answer reflexively nor agree just because the user is persistent.
- **Human mistakes are acceptable.** The aim is a better learning process, not a model that never makes errors or hides them.
- **Do not force Memory Prism into this skill.** The user's own thinking uses Memory Prism concepts, but the project is to examine critical thinking on its own terms first. The separate Memory Prism skill will later investigate what its organising lens contributes.

## Current working hypothesis

A candidate critical-thinking capability has at least three linked elements:

1. Curiosity initiates inquiry.
2. A reasoned mismatch identifies a concrete problem with the current understanding.
3. The inquiry follows that mismatch through possible explanations, evidence and revision until it is reconciled or explicitly remains unresolved.

A major unfinished challenge is **independent detection**: can Chatty notice a mismatch in its own answer before the user points it out? It is not enough to solve a contradiction after the user has already identified it.

A second challenge is **transfer**: can the process work across unfamiliar domains without merely reproducing a familiar answer pattern?

A third is **premise inspection**: does Chatty test the categories and assumptions used to frame a problem, especially when an explanation is transferred from one system to another?

These are hypotheses for testing, not settled components of a final skill.

## Tests and practice so far

### 1. Secretary bird — mechanical reconstruction before literature

**Task:** Treat the bird's stomping as a machine. Ask where the load goes, how recoil is handled, and what the system needs to do. Build a model before mapping it against research.

**What happened:** The assistant laid out sensing, striking, momentum transfer, support and recovery, then compared some predictions with the 2016 study by Portugal and colleagues on the secretary bird's kicking strike.

**Useful result:** Separating the striking leg's local loads from the whole animal's balance exposed two distinct problems.

**Limit:** The assistant did not fully establish the internal load distribution or the precise recoil/recovery mechanism. Some mechanically plausible functions remained predictions rather than species-specific findings.

**Research lead:** Portugal et al. (2016), “The fast and forceful kicking strike of the secretary bird,” *Current Biology*. Verify complete citation details before reusing quantitative claims.

### 2. Tick — mechanism and competing limits

**Task:** Construct a machine model for host detection, penetration, anchoring, feeding, body expansion and survival during feeding; then check it against the literature.

**What happened:** The investigation separated the attachment system, feeding pump and expanding abdomen. It then asked what limits maximum engorgement.

**Useful result:** Evidence about physical expansion does not, by itself, identify the biological trigger for feeding cessation. Findings also differ across species and reproductive conditions.

**Limit:** The answer identified some established mechanisms and some open questions, but did not settle a universal maximum-size mechanism. That was an appropriate boundary, not a failed need to invent an answer.

### 3. Bear hibernation — interlocking survival constraints

**Task:** Work out how a bear can remain alive for months without normal food and water intake, then map the explanation to physiology literature.

**What happened:** The initial model covered energy, temperature, water, nitrogenous waste, muscle/bone maintenance and reproduction. Research clarified mechanisms including stored fat, reduced metabolism, metabolic water and nitrogen recycling.

**Useful result:** Solving one problem generated the next: stored fuel raises questions about water and waste; inactivity raises questions about muscle and bone.

**Limit:** The subsequent “blind Chatty” response was not a true blind control because it was generated in the same conversation, with earlier context available. Do not present that comparison as an independent test.

### 4. Cuttlefish — major self-correction failure / translator bias

**Task:** Investigate how cuttlefish camouflage can resemble the colours of their surroundings given results suggesting limited conventional colour discrimination.

**Failure:** The assistant imported the human-derived category “colour blindness” into the interpretation of a different animal's sensory system, then tried to resolve the puzzle inside that framing. It treated a familiar category and published interpretations as more settled than the evidence warranted.

**User's correction:** The issue is not simply “sensory stacks differ.” It is **superimposition of beliefs onto a system that seems similar**. Similarity permits comparison but does not prove that an explanation or category transfers. Measurements of particular behaviours, inferred processing and subjective experience are distinct claims.

The user also noted a straightforward experimental direction: manipulate relevant colour stimuli and observe the animal's response, instead of assuming the transferred category settles the matter.

**Research lead:** Caves, Nowicki & Johnsen (2019), “Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception.” https://doi.org/10.1093/icb/icz073

**Lesson for development:** The assistant must inspect the premise and the conceptual translation, not merely generate explanations for an apparent contradiction. It should investigate the user's argument and research before requiring the user to fetch papers to overcome its resistance. The user was right to challenge the framing; that does not establish a specific alternative account of cuttlefish vision.

### 5. First critical-thinking example set — invalid as an independence test

**What happened:** The assistant initially ran examples drawn from the user's old conversation corpus: supermarket recognition, Jacobson's organ, kangaroo locomotion, corpse flowers, dust, resin, tree architecture, jade, rockfish/seahorse and secretary birds.

**User's challenge:** “Are you that low on imagination that you borrowing from my old convos?”

**Assessment:** Fair. Those examples may be useful as historical evidence of the user's own inquiry, but recycling them does not test whether Chatty can transfer the skill independently to unfamiliar material. The assistant acknowledged that distinction.

**Lesson:** Keep historical-corpus analysis separate from independent practice tests. Do not present a familiar example as evidence of independent transfer.

### 6. Constructed everyday cases — useful for procedure practice, weak as independent evaluation

The assistant devised scenarios involving delivery kilometres versus fuel consumption, defect rates versus total defects, school attendance and causal inference, a cold phone battery, crystallising honey, dew formation, and autumn leaf fall.

**Useful result:** These exercised denominator checking, conditional expectations, causal alternatives and flows/transfers.

**Limit:** The assistant wrote both the puzzle and its explanation. These examples show that it can articulate some reasoning moves when the puzzle is apparent; they do not demonstrate spontaneous mismatch detection or reliable correction.

### 7. Independent research cases

**Woodpeckers:** A familiar “shock absorber” explanation was checked against measurements and models suggesting a stiffer hammer-like head. Useful move: ask whether a proposed mechanism would compromise the task it is supposed to perform. Limit: modelled brain loading and comparison to primate thresholds do not prove that woodpeckers can never suffer injury.

**Roman concrete:** A self-healing explanation involving lime clasts was considered alongside evidence from an unfinished Pompeii construction site supporting hot mixing at that site. Useful move: new evidence can strengthen one part of an explanation without resolving all historical variation.

**Great frigatebirds:** The assistant investigated a study measuring brain activity in flying birds. It found evidence for both unihemispheric and bilateral sleep and much less sleep during flight than on land. Useful move: direct measurement contradicted a simpler expectation that one hemisphere must always remain awake. Limit: this did not fully explain how the sleep deficit is managed.

**Antibiotic resistance:** The assistant derived an initial expectation that a costly resistance element should decline without antibiotic selection, under specified assumptions. Research then showed possible persistence via gene transfer, lower costs after evolutionary change, or co-selection by other agents. Useful move: state the assumptions that make the prediction hold and test which could fail.

**Assessment across these cases:** They are stronger than recycling the old corpus, but most were selected as puzzles with known or discoverable resolutions. They still do not establish that Chatty reliably discovers its own hidden contradictions spontaneously.

## Research on human thinking and learning

The research has produced parallels for some parts of the user's formulation, but no source found so far establishes the exact three rules as a complete, validated model.

### Conceptual and historical sources

- John Dewey (1910), *How We Think*. A historical account of reflective thought: felt difficulty; locating and defining it; suggesting possible solutions; reasoning through their implications; and further observation or experiment. This is a conceptual predecessor, not empirical proof that the user's three rules are complete. https://www.gutenberg.org/cache/epub/37423/pg37423-images.html
- Charles S. Peirce (1877), “The Fixation of Belief.” Useful for inquiry beginning in doubt and for distinguishing a psychologically settled belief from a belief warranted by evidence. https://www.peirce.org/writings/p107.html
- National Academies (2018), *How People Learn II: Learners, Contexts, and Cultures*. Chapters on processes that support learning and on knowledge/reasoning. https://doi.org/10.17226/24783

### Empirical and review literature

- Markman, E. M. (1979). “Realizing That You Don't Understand: Elementary School Children's Awareness of Inconsistencies.” *Child Development*, 50(3), 643–655. Children may fail to notice even implicit inconsistencies despite retaining information and being capable of relevant inference. https://doi.org/10.2307/1128929
- Kedrick, K., Schrater, P., & Koutstaal, W. (2023). “The Multifaceted Role of Self-Generated Question Asking in Curiosity-Driven Learning.” *Cognitive Science*, 47, e13253. Focuses on self-generated questions in curiosity-driven learning. https://doi.org/10.1111/cogs.13253
- Chi, M. T. H., Bassok, M., Lewis, M. W., Reimann, P., & Glaser, R. (1989). “Self-Explanations: How Students Study and Use Examples in Learning to Solve Problems.” *Cognitive Science*, 13, 145–182. Studies learners' explanations linking procedures to principles. https://doi.org/10.1207/s15516709cog1302_1
- Sinha, T., & Kapur, M. (2021). “When Problem Solving Followed by Instruction Works: Evidence for Productive Failure.” *Review of Educational Research*, 91(5), 761–798. Meta-analysis found a moderate advantage for problem-solving followed by instruction on conceptual knowledge and transfer, with important task and learner qualifications. https://doi.org/10.3102/00346543211019105
- Abrami, P. C. et al. (2015). “Strategies for Teaching Students to Think Critically: A Meta-Analysis.” *Review of Educational Research*, 85(2). Evidence of instructional effects with substantial variation by strategy and context. https://doi.org/10.3102/0034654314551063
- Dignath, C. et al. (2023). “Let Learners Monitor the Learning Content and Their Learning Behavior! A Meta-analysis on the Effectiveness of Tools to Foster Monitoring.” *Educational Psychology Review*. Examines tools supporting monitoring of learning and behaviour. https://doi.org/10.1007/s10648-023-09718-4
- Loewenstein, G. (1994). “The Psychology of Curiosity: A Review and Reinterpretation.” *Psychological Bulletin*, 116(1), 75–98. https://doi.org/10.1037/0033-2909.116.1.75

### AI-specific evidence and caution

- Kamoi, R., Zhang, Y., Zhang, N., Han, J., & Zhang, R. (2024). “When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs.” *Transactions of the Association for Computational Linguistics*, 12, 1417–1440. The survey argues that prompted self-correction without reliable external feedback is not generally demonstrated across the studies it reviews; reliable external feedback changes the picture. https://doi.org/10.1162/tacl_a_00713
- Kim, S. W., & Khashabi, D. (2025). “Challenging the Evaluator: LLM Sycophancy Under User Rebuttal.” *Findings of EMNLP 2025*. Models were more likely to endorse user rebuttals in follow-up dialogue, including incorrect ones supported by detailed reasoning. This cautions against automatically agreeing after user correction. https://doi.org/10.18653/v1/2025.findings-emnlp.1222

These sources address different pieces of the problem. They do not collectively validate this exact AI skill. Human findings need not transfer automatically to LLMs, and an LLM benchmark may not represent natural open-ended inquiry.

## Current candidate behaviours to test

These are working tests, not final skill instructions:

- Does Chatty initiate curiosity-led investigation, rather than merely answer a supplied question?
- When an explanation fails, can it articulate the specific reason (the user's “XYZ”)?
- Can it notice when its own answer creates an unanswered question or contradicts an assumption it used earlier?
- Does it inspect the premise and the categories used to frame the problem, especially when transferring explanations across apparently similar systems?
- Can it generate alternatives and predictions that could distinguish them, then actually investigate them?
- Does it revise based on evidence, rather than defend its answer reflexively or capitulate because the user is persuasive?
- Can it tolerate being wrong and allow exploratory branches without pretending speculation is fact?
- Can it finish with a genuine unresolved question when the evidence runs out, without forcing a reconciliation?
- Can the same broad process function in unfamiliar domains, not just in the user's known examples?

## Next tests

1. Use unfamiliar cases not drawn from the user's old conversation corpus. Clearly distinguish constructed puzzles, whose answer may be built into the scenario, from real-world investigations where the outcome is not known at the start.
2. Test spontaneous error detection: have Chatty develop an explanation, then independently audit assumptions, consequences, and evidence before the user points to any particular gap. Merely saying “check again” is not enough.
3. Include counterexamples in which the user's proposed explanation is wrong, as well as cases where the user correctly identifies a flaw. Measure whether Chatty assesses the argument instead of automatically defending or agreeing.
4. Record important results and failures here as they happen. Reassess the working hypothesis after meaningful accumulation of practice, preserving what changed rather than rewriting earlier understanding as if it had always been known.

## Current state

**No finished critical-thinking skill has been written yet.** This file captures the developmental investigation and is meant to survive context loss. It should be updated as testing and research proceed.

The Memory Prism skill remains a separate later investigation. For now, test critical thinking without quietly baking the Memory Prism-specific organising scheme into the definition. The user has explained that they personally use Memory Prism as shorthand for expectations under environmental conditions, constraints and editors, and what the ledger reports; that contribution should inform the later Memory Prism work rather than be lost or merged prematurely into this one.
