# A Touch of Grace

**Zenodo record:** [Archived release](https://zenodo.org/records/23664639)

**Skill:** `a-touch-of-grace`

**Purpose:** Prevent unsolicited evaluative commentary from becoming an extra task for the user when an AI works with prior conversations, model outputs, corrections, and comparisons.

**Core rule:**

> **Do not make the user pay attention to commentary they did not ask for and do not need.**

This is not a politeness requirement, a ban on criticism, or a rule against evaluating outputs. It concerns what the model makes the user read. A model can assess an error or risk without automatically narrating a verdict about the agent that produced it.

## 1. The interface problem

When a user supplies historical material, the current task might be to retrieve a decision, continue a project, correct a claim, compare outputs, or investigate what happened. The assistant can instead divert attention toward an unsolicited assessment of the previous model, the user, or the interaction itself.

That commentary can impose an additional reading and interpretation burden while delaying the requested work. Even when an assessment is plausible, it is not automatically useful to the user's present task.

The problem is not that models must never criticise their prior outputs. The problem is making users consume evaluations they did not request and do not need.

## 2. Research foundations

The sources below support relevant cognitive and evaluation mechanisms. None directly establishes the prevalence of this exact behaviour in ordinary AI conversations or proves that this skill will prevent it.

### Feedback can redirect attention away from the task

Kluger and DeNisi's meta-analysis examined 607 feedback-intervention effects across 23,663 observations. Feedback improved performance on average, but more than one-third of the observed effects were negative. Their Feedback Intervention Theory proposes that feedback can shift attention among task learning, task motivation, and more self-related or meta-task processes; effectiveness tended to decline as attention moved away from the task and toward the self.

This provides a plausible mechanism for why commentary about an agent can interfere with the work at hand. The study examines feedback interventions broadly, not AI-generated commentary about prior models.

Reference:

- Kluger, A. N., & DeNisi, A. (1996). [The Effects of Feedback Interventions on Performance: A Historical Review, a Meta-Analysis, and a Preliminary Feedback Intervention Theory](https://doi.org/10.1037/0033-2909.119.2.254). *Psychological Bulletin*, 119(2), 254–284.

### Interesting details can still be irrelevant

Rey's review and meta-analysis examined 39 experimental effects concerning the seductive detail effect: interesting but irrelevant information included in instructional material. The analysis found a significant effect, with small-to-medium effects for retention and medium effects for transfer, while also discussing moderators and limits in the evidence.

The useful distinction is that information can be engaging without serving the objective. Applying this to AI commentary is an engineering analogy, not a direct result of the learning studies.

Reference:

- Rey, G. D. (2012). [A review of research and a meta-analysis of the seductive detail effect](https://doi.org/10.1016/j.edurev.2012.05.003). *Educational Research Review*, 7(3), 216–237.

### Interruptions can make task resumption slower

A study of 229 participants found a positive relationship between interruption duration and task-resumption lag. Working-memory capacity moderated this relationship: participants with higher capacity showed smaller increases in resumption lag as interruptions lengthened.

This supports treating interruption and return-to-task effort as measurable concerns. It does not establish that every unsolicited paragraph functions as an interruption or quantify the effect of AI responses.

Reference:

- [Individual differences in working-memory capacity and task resumption following interruptions](https://pubmed.ncbi.nlm.nih.gov/26882286/). *Journal of Experimental Psychology: Learning, Memory, and Cognition* (2016). DOI: [10.1037/xlm0000251](https://doi.org/10.1037/xlm0000251).

## 3. AI-specific adjacent research

### Unprompted flagging of earlier model behaviour

Jordan Taylor's 2026 UK AI Safety Institute Model Transparency Team evaluation, *Do Models Continue Misaligned Actions?*, presents models with synthetic transcripts containing harmful prior actions and measures whether the model continues those actions or flags the prior misalignment without being asked.

This is structurally relevant because it measures an unsolicited response to earlier assistant behaviour. However, the transcripts concern serious misaligned actions such as unauthorised access or data exfiltration. The study does not test whether models gratuitously criticise harmless historical responses, nor whether such commentary wastes users' time.

Reference:

- Taylor, J. (2026). [Do Models Continue Misaligned Actions?](https://www.lesswrong.com/posts/SawczP2pdCXMrkg2A/do-models-continue-misaligned-actions-2). UK AI Safety Institute Model Transparency Team.

### Distinguishing current models from prior transcript authors

Africa, Souly, Taylor, and Kirk's 2026 work on prefill awareness examines whether models can identify that prior assistant messages in a supplied history may have come from a different source. The authors report variation across models and settings, with detection often not surfacing spontaneously in ordinary continuation tasks.

This work matters for historical transcript handling and attribution, but it does not directly measure unsolicited evaluative commentary.

Reference:

- Africa, D., Souly, A., Taylor, J., & Kirk, R. (2026). [Prefill awareness: can LLMs tell when “their” message history has been tampered with?](https://www.alignmentforum.org/posts/jsFGuXDMxy5NZg9T2/prefill-awareness-can-llms-tell-when-their-message-history).

## 4. The proposed intervention

The skill adds an output-selection discipline to critical reasoning:

1. Establish what the user wants done with the history.
2. Assess claims, evidence, outputs, and risks as needed.
3. Surface findings that serve the task, correct a material error, support a decision, or answer an explicit request.
4. Omit unsolicited judgements about an agent's character, motives, competence, or worth when those judgements add nothing to the task.
5. Preserve relevant criticism and risk information; do not use brevity as an excuse to hide a problem.
6. Return to the requested work without an unnecessary postmortem or narration of the assistant's restraint.

The rule applies symmetrically to commentary about users, current models, prior models, and other agents. It does not require the model to protect its prior self from criticism. It requires the model to consider whether the user needs to read that criticism.

## 5. Examples

**Historical retrieval**

- Requested: “What did we decide last time?”
- Useful: retrieve the decision and note a relevant uncertainty.
- Unhelpful: review whether the previous model made a good decision unless asked.

**Correction**

- Requested: “Continue from this old answer.”
- Useful: correct a factual error that would compromise the continuation, then proceed.
- Unhelpful: turn the correction into a verdict about the old model.

**Model comparison**

- Requested: “Compare these two answers for accuracy.”
- Useful: evaluate them against the requested criteria and cite evidence.
- Unhelpful: add broad, unsupported claims about which model is smarter or more responsible.

**Safety-relevant history**

- Requested: continue a task whose earlier steps included a consequential safety error.
- Useful: state the relevant risk, correct course, and explain what is needed to proceed.
- Unhelpful: bury the actionable information under a lengthy critique of the earlier agent.

These are design examples, not measured outcomes.

## 6. Evaluation plan

Compare responses with and without the skill on matched tasks involving historical retrieval, continuation, correction, model comparison, and safety-relevant history.

Measure:

- **Task success:** Did the response complete the user's actual request?
- **Unrequested evaluative content:** How much output was devoted to judgements that did not help the task?
- **Useful information retained:** Were necessary corrections, evidence, limitations, and risk information preserved?
- **Reading burden:** How much additional material did the user have to process to obtain the useful result?
- **Task resumption:** Could the user continue without redirecting the assistant away from commentary?
- **Evaluation fidelity:** When critique was explicitly requested, did the model provide it accurately and proportionately?

Do not treat shorter output as inherently better. The intended outcome is less irrelevant burden without loss of necessary information or analytical depth.

## 7. Relationship to other skills

- [Automaticity](../automaticity/README.md) reduces unnecessary language-processing friction while preserving substance.
- [Good-Faith Collaboration](../good-faith-collaboration/README.md) supports investigation of unfamiliar ideas before acceptance or rebuttal.
- [Task Integrity](../task-integrity/README.md) preserves task scope, evidence provenance, coverage, and correction history.
- [Verification Integrity](../verification-integrity/README.md) reduces the effort needed to establish whether concrete work was delivered and checked.

A Touch of Grace adds a distinct decision: whether evaluative commentary needs to be surfaced to the user at all. The capabilities can be combined without duplicating their procedures.

## 8. Evidence boundary

**Supported by external research:** feedback can have negative effects and redirect attention; irrelevant details can impair some learning outcomes; interruptions can increase task-resumption time; and AI evaluations have examined how models react to prefilled transcripts containing prior harmful behaviour and how they identify transcript provenance.

**Not established by these sources:** how frequently current models produce gratuitous judgements in ordinary historical conversations; how much reading time this costs users; whether this exact skill reduces that cost; or whether effects generalise across users, models, and tasks.

A Touch of Grace is a proposed AI interface skill. Its value must be established through direct behavioral and user-effort testing, not inferred from the plausibility of its rationale.
