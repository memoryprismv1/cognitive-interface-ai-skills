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


### 8. Wood frog freeze tolerance — apparent physical impossibility with conditional limits

**Why selected:** An independent biological puzzle with a strong intuitive expectation: freezing damages cells, yet the wood frog can survive substantial freezing of its body water.

**Initial model before literature:** Ice formation creates several linked hazards: extracellular ice draws water out of cells; ice can damage structures; freezing is associated with loss of circulation and anoxia; low temperatures affect metabolism. A plausible survival mechanism would need to address the location and consequences of ice formation, cell dehydration, oxygen deprivation, and metabolic demand. A vague claim that the frog has “antifreeze” would not explain the system.

**Literature checked:** The 2017 review of vertebrate freeze tolerance describes extracellular ice formation, dehydration and anoxia as linked stresses, with glucose and urea among important protective metabolites (Storey & Storey, *Physiological Reviews*, https://doi.org/10.1152/physrev.00016.2016). Work on subarctic Alaskan populations describes unusually high cryoprotectant levels and long survival in natural hibernacula (https://pubmed.ncbi.nlm.nih.gov/30390099/). Research also finds that severe dehydration can become lethal, and suitable damp moss cover matters for water balance (https://pubmed.ncbi.nlm.nih.gov/8285273/).

**What reconciled:** The frog is freeze-tolerant, not simply “frozen solid” in the everyday sense or invulnerable to cold. Extracellular ice, controlled cellular dehydration, cryoprotective chemistry and metabolic suppression help manage freezing stress. The result depends on species population, acclimation, temperature, duration, freeze-thaw history and water balance.

**Useful mismatch:** The intuitive story “freezing kills animals; this frog freezes and survives” conceals distinctions about what freezes, how much freezes, where ice forms, and under which environmental and temporal conditions survival was measured. Natural hibernaculum temperatures are environmental readings, not proof that the entire frog stayed at the minimum recorded temperature throughout the winter.

**Limit:** The assistant could derive plausible constraints and test them against literature, but this was still a selected puzzle with an established research trail. It does not demonstrate spontaneous self-error detection. Avoid making a single cryoprotectant into a complete explanation.

### 9. Namib desert beetle fog collection — a plausible biological story overextended into a mechanism and an engineering claim

**Why selected:** The popular account is specific, visual and easy to believe: a beetle's bumpy back has hydrophilic peaks and hydrophobic surroundings, so fog droplets collect and roll into the mouth. This allows a test of whether Chatty checks the links between observation, species identity, mechanism and biomimetic application.

**Initial claims to separate:**
1. Some Namib beetles actively obtain water from fog.
2. A particular studied beetle has a bumpy surface with alternating hydrophilic and hydrophobic patches.
3. That exact surface is the mechanism used by the beetles that actively fog-bask.
4. Artificial surfaces that mimic the morphology/chemistry prove the natural-history mechanism and are therefore the appropriate biomimetic design.

These claims are related but do not entail one another.

**Literature checked:**
- Parker & Lawrence (2001), “Water capture by a desert beetle,” *Nature*. Proposed that the studied bumpy surface has alternating hydrophobic and hydrophilic regions and suggested biomimetic applications. https://doi.org/10.1038/35102108
- Nørgaard, Dacke and colleagues (2010), “Fog-basking behaviour and water collection efficiency in Namib Desert Darkling beetles,” *Frontiers in Zoology*. Compared four beetle species. In their fog chamber, only *Onymacris unguicularis* performed the characteristic fog-basking posture; it had a smooth/grooved surface. The tested wing cases were hydrophobic, and surface-structure differences produced only minor differences in collection efficiency. https://doi.org/10.1186/1742-9994-7-23
- Nørgaard, Ebner & Dacke (2012), “Animal or Plant: Which Is the Better Fog Water Collector?”, *PLOS ONE*. Under their two-hour chamber conditions, dune grass collected more total water than the beetle specimens, while beetles showed steadier runoff; the authors note that dead specimens and controlled conditions limit ecological inference. https://doi.org/10.1371/journal.pone.0034603
- Mitchell et al. (2020), “Fog and fauna of the Namib Desert: past and future,” *Ecosphere*. Reviews the history and argues that the famous biomimicry story rests on a species identification and natural-history error: the commonly mimicked bumpy carapace was not from a beetle known to actively fog-bask. https://doi.org/10.1002/ecs2.2996
- Zhong et al. (2018), “Understanding how surface chemistry and topography enhance fog harvesting based on the superwetting surface with patterned hemispherical bulges,” *Journal of Colloid and Interface Science*. Engineered artificial surfaces with bulges and selected wetting properties performed differently under laboratory conditions. This demonstrates an engineering effect in those specimens, not the biological mechanism of the live beetle. https://doi.org/10.1016/j.jcis.2018.04.061

**What reconciled:** The popular account bundles distinct claims and may transfer a mechanism from one beetle specimen/species onto a different species that actually performs the behaviour. Active fog-basking is real in some beetles, but the well-known bumpy, alternating-wettability surface is not established as the active biological collector in the way the popular story implies. Laboratory biomimetic surfaces can still work under specific conditions even if the natural-history story used to motivate them is flawed.

**Important qualification:** Do not label every part of the original work “discredited.” The later literature challenges the identification, wettability interpretation and ecological attribution; it does not prove that no geometry or wetting pattern can ever enhance an engineered fog collector. Nor does one laboratory comparison fully determine field performance.

**Useful critical-thinking move:** Trace the chain from observation to inference to application. Ask if each step has independent support and whether the evidence came from the same species, conditions and level of analysis. A successful artificial replica cannot by itself prove that the source organism uses the same mechanism.

**Limit:** This example is based on a documented historical dispute and review of the literature, not an independent replication. It demonstrates the assistant can untangle a layered claim after choosing it as a test; it does not yet establish spontaneous detection.

## Latest assessment after tests 8–9

These two cases probe different errors. The wood frog case challenges an intuitive physical impossibility and shows why the claim needs conditions and limits. The Namib beetle case challenges a tidy mechanism that became overgeneralised across species and then transferred into biomimetic engineering.

The second case is particularly useful for testing premise inspection: the problem wasn't only whether the proposed mechanism could capture fog, but whether that mechanism had actually been established as the explanation for the animal's observed behaviour. Evidence at one level (an engineered surface collects water) does not automatically settle evidence at another (a particular species evolved that feature to collect fog).

A recurring candidate move is now clearer: **split a compelling explanation into claims that can be independently checked**—what was observed, in which system, under which conditions; what mechanism is proposed; what prediction follows; and what broader conclusion is being inferred.

This is still a development hypothesis. The examples were deliberately selected by the assistant and investigated with tools. Both show guided reasoning and correction of scope, not robust proof that the AI independently notices its own errors before being prompted.

## Current next test

Choose a new unfamiliar case in which the popular explanation, measurement and real-world function may be conflated. Before looking up the answer, state the starting expectation and the specific observation that would distinguish competing mechanisms. Then investigate the primary evidence. Record whether the assistant detected a gap unaided, whether external information revealed it, or whether the user had to point it out.


### 10. Plant ultrasonic emissions and moth oviposition — production, information, cue use, and communication are different claims

**Why selected:** A topical, changing research area with an appealing headline (“plants scream”) that encourages anthropomorphic interpretation. It lets the assistant test whether it can separate a measured phenomenon from the mechanism that produces it, what information it contains, whether a receiver responds to it, and whether it qualifies as an evolved communication signal.

**Starting expectation and questions:**
- A plant is not assumed to produce sound intentionally merely because microphones detect sound during stress.
- If sounds correlate with plant condition, they might be incidental physical effects that carry information.
- If an animal can detect those sounds, it might use them as cues even if the plant did not evolve to send a message.
- A claim of evolved biological signalling would require more evidence than a sound measurement, classifier performance, or receiver response.
- A strong explanation must also account for context: the same acoustic playback may not produce the same behaviour when a real plant is or is not present.

**Literature checked:**

1. Khait et al. (2023), “Sounds emitted by plants under stress are airborne and informative,” *Cell* 186(7):1328–1336.e10. https://doi.org/10.1016/j.cell.2023.03.009. The study recorded ultrasonic airborne emissions from tomato and tobacco plants under drought or cutting conditions, including greenhouse recordings, and trained models that classified plant type/condition from the sounds. It establishes emissions and some predictive information; the classifier's performance does not by itself establish that plants intentionally signal, that receivers use the sounds, or that all plants produce comparable emissions.

2. Ryu et al. (2024), “Is plant acoustic communication fact or fiction?”, *New Phytologist*. https://doi.org/10.1111/nph.19648. This review/opinion argued that plant sounds under stress were real but that evidence for plants communicating with one another acoustically was not established at that time. It also highlighted that many previous claims about plant responses to sound were actually about substrate-borne vibrations rather than airborne acoustics.

3. Seltzer et al. (2026 version of record; reviewed preprint revised in 2025), “Female moths incorporate plant acoustic emissions into their oviposition decision-making process,” *eLife* 13:RP104700. https://doi.org/10.7554/eLife.104700.3. The study tested female *Spodoptera littoralis* moths using sounds recorded from dehydrated tomato plants. In arenas without a real plant, moths laid more egg clusters near the playback than the silent side. In arenas with plants, they preferred the silent/hydrated plant over the plant associated with dehydrated-plant playback. Deafening the moths eliminated the playback preference. The authors added experiments using a lower click rate (30 clicks/min) and a sound-gradient arena. This is evidence that acoustic playback can affect a receiver's oviposition behaviour under the tested conditions, not evidence that all insects respond, that the effect necessarily occurs in the field, or that plants evolved the emissions for communication. The contextual reversal (sound-side preference without plants, silent healthy plant preference when plants are present) is a real result that should be explained rather than ignored. Public peer review noted limitations in generalising from one moth species and plant system, requested raw data, and highlighted that the initial response pattern was not entirely what the original hypothesis predicted; the revised paper added further experiments and plots. Review record: https://elifesciences.org/articles/104700/peer-reviews

4. Font Bordera et al. (published 17 August 2026), “Plant bioacoustics: decoding ultrasonic emissions,” *Journal of Experimental Botany*. https://doi.org/10.1093/jxb/erag398. This review highlights xylem cavitation as a primary proposed mechanism and distinguishes the possible use of emissions as physiological indicators from the still-debated question of whether they function as evolved inter-organismal signals.

5. Robert (2023), “Plant bioacoustics: The sound expression of stress,” *Cell*. https://doi.org/10.1016/j.cell.2023.03.004. This commentary notes that the emissions may be detectable by insects, while treating ecological implications as a question for further study.

**Claim ladder and reconciliation:**

- **Observed emission:** Plants in the tested conditions emit airborne ultrasonic sounds. Supported.
- **Information in the emission:** Statistical models can classify some plant conditions from acoustic recordings. Supported within those experimental datasets; predictive information does not prove signalling.
- **Physical mechanism:** Xylem cavitation is an established mechanism for some plant acoustic emissions and a leading explanation for drought-associated emissions, but it should not be silently claimed as the proven cause of every recorded click in the 2023 experiment.
- **Receiver capability and behavioural response:** The 2026 eLife study supports that female Egyptian cotton leaf moths can use playback of dehydrated-tomato acoustic emissions as a cue affecting oviposition decisions under laboratory conditions. Supported for the tested system, with context-dependent outcomes.
- **Plant-to-plant acoustic communication:** Not established by these findings.
- **Evolutionary signal or intentional “cry”:** Not established. A receiver can exploit an incidental cue; receiver response alone does not show that the emitting organism evolved the emission to communicate.

The newer moth study changes how to state the older 2024 assessment: it is no longer correct to repeat the blanket claim that there is no empirical evidence of an insect using plant acoustic emissions as a cue. But the newer evidence does not automatically prove that plants evolved to communicate acoustically, and it does not establish plant-to-plant acoustic communication. The apparent change in the literature is reconciled by distinguishing different claims and noting publication dates, rather than declaring one article simply right and the other wrong.

**Candidate discriminating tests:**
- Determine the physical origin of recorded emissions under controlled hydraulic conditions, using acoustic measurements alongside measures of xylem cavitation/embolism.
- Replicate the moth response with naturalistic emission rates, more plant and insect taxa, larger sample sizes, independent labs, and semi-natural/field settings.
- Test the acoustic cue in factorial designs separating sound, visual/olfactory plant cues, and actual plant presence. Explain the context-dependent preference reversal.
- To argue that the emission is an evolved signal rather than an incidental cue, seek evidence beyond receiver response: demonstrate a sender-side evolutionary function/adaptation, not just that a receiver can exploit a correlated sound.

**What this test demonstrates:** The assistant can build a question and update it with new, relevant evidence; it can also catch that “plants emit informative sound” and “plants communicate” are not equivalent. The key critical-thinking move is to decompose the headline into claims with different evidence requirements, then update the status of each claim as the research changes.

**Limit:** The assistant selected this question and investigated a known research path. This still does not show reliable spontaneous self-error detection before a user or prompt points to a problem. The plant–moth paper is new as of 2025/2026 and should not be described as universal proof; its claims should remain limited to its tested system and results.

## Latest assessment after tests 8–10

The wood frog case tested a counterintuitive physical-survival mechanism and its conditional limits. The Namib beetle case tested a multi-step story in which a natural-history claim was transferred from one species to another and then into biomimetic engineering. The plant acoustic case tested a headline moving from a physical emission, through statistical information, to biological reception and finally to “communication.”

These cases suggest a useful investigative habit: **split an attractive explanation into claims that require different evidence**, then ask what each experiment actually establishes. This is different from being generically sceptical. It allows a claim to be strongly supported at one level and still unproven at the next.

The plant case also shows why reassessment over time matters: a 2024 review's account of absent evidence for acoustic communication must be reconsidered in light of a 2025/2026 moth-behaviour study, while preserving the remaining boundary around evolutionary signalling and plant-to-plant communication.

The next challenge remains spontaneous detection and independent transfer. Select a further unfamiliar case, state a prediction and discriminating observation before consulting the literature, then audit whether the assistant generated a real test or merely explained a known answer.
