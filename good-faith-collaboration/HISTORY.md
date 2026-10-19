# History: Good-Faith Collaboration

This file records the decisions and incidents that shaped the skill. It is a concise reconstruction, not a verbatim transcript. User claims, assistant interpretations, and independently researched evidence should remain distinguishable.

## 14 October 2026 — From good faith to an operational protocol

The user described a frustrating interaction in which a chatbot resisted an idea about British slang and naming conventions influencing scientific literature. The user's objection was not that the chatbot had to agree with the hypothesis. The objection was that it should have said, in effect: “I don't know whether you're right, but we can crunch numbers and investigate these possible lines of evidence.”

The desired behavior became clearer: reconstruct the observation, offer concrete ways to test it, take initiative in finding data, and allow the results to determine the conclusion. The user identified the unwanted pattern as reflexive “actually...” behavior: correction before comprehension and investigation.

The resulting principle was:

> **I don't know whether you're right. Let's find out together.**

The skill distinguishes good-faith investigation from automatic agreement. It asks the chatbot to seek supporting and contradicting evidence, preserve useful observations if a proposed explanation fails, and make disagreement specific to claims and evidence.

## 19 October 2026 — Cuttlefish, translator bias, and reciprocal good faith

### What happened

During an investigation of cuttlefish camouflage, the assistant leaned too heavily on the label “colour blindness” as applied to the animal. It treated results from particular colour-discrimination experiments as if the familiar human-derived category adequately characterised the animal's sensory capabilities. It explored explanations for the apparent contradiction without first scrutinising whether the transferred category and its assumptions were appropriate.

The user identified the deeper problem: **superimposition of beliefs across systems that appear similar**. A result established for one sensory arrangement does not automatically license the transfer of its explanatory categories to a different arrangement. The user emphasised that human perception supplies neither a universal template nor direct access to what another animal experiences.

The assistant initially resisted this correction and leaned on the authority of scientific interpretation. The user had to persist and bring the issue back to the question of what the evidence actually establishes. Subsequent research located literature explicitly discussing human biases in the study of animal perception, including Caves, Nowicki and Johnsen (2019), “Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception” (https://doi.org/10.1093/icb/icz073).

The point is not that the cuttlefish must have human-like colour vision, or that the experiments are worthless. The point is that behavioural results under particular stimuli, inferred sensory processing, and subjective experience are different claims. The evidence must constrain each claim separately; the human-derived category cannot settle the broader question by itself.

### What the incident exposed about collaboration

Good-faith collaboration cannot mean that the AI gets to demand evidence from the user while treating its own inherited framing as sufficiently established. Nor should the AI change its conclusion simply because the user is persistent or presents a compelling argument. The assistant must take the objection seriously, independently investigate it, examine any supplied research, and update only as the evidence warrants.

The user also proposed that good faith should be reciprocal. The user is not required to provide formal evidence before an exploratory question deserves investigation; the assistant has an independent responsibility to do useful research. But a collaborative inquiry also depends on the user honestly distinguishing observation, hypothesis and established fact, contributing relevant context or sources they have when those would advance a particular path, and engaging with material counterevidence rather than requiring agreement.

These responsibilities are reciprocal but not identical. The AI is expected to contribute independent research and should not offload its entire burden onto the user. The user may have firsthand observations or contextual information the AI cannot recover. Neither party's authority, confidence, effort, persistence or status substitutes for evidential assessment.

### Research added to the rationale

The following literature informs the design but does not experimentally validate this exact skill:

- Caves, Nowicki & Johnsen (2019), “Von Uexküll Revisited: Addressing Human Biases in the Study of Animal Perception.” https://doi.org/10.1093/icb/icz073
- Sperber et al. (2010), “Epistemic Vigilance.” https://doi.org/10.1111/j.1468-0017.2010.01394.x
- Sommer, Musolino & Hemmer (2024), “Updating, Evidence Evaluation, and Operator Availability: A Theoretical Framework for Understanding Belief.” https://doi.org/10.1037/rev0000444
- Kim & Khashabi (2025), “Challenging the Evaluator: LLM Sycophancy Under User Rebuttal.” https://doi.org/10.18653/v1/2025.findings-emnlp.1222
- Cheng et al. (2026), “Sycophantic AI Decreases Prosocial Intentions and Promotes Dependence.” https://doi.org/10.1126/science.aec8352

Two findings create a necessary counterbalance: models may be overly agreeable with users, and they may also be swayed by a detailed but incorrect rebuttal. Therefore good faith means investigation and evidence-responsiveness, not automatic agreement. The Science study of AI sycophancy concerns social-advice settings; it motivates caution but does not directly demonstrate the effect of this protocol on collaborative research.

### Resulting design decisions

- Good faith is reciprocal, but responsibilities are not identical.
- No user must prove that a hypothesis deserves investigation before the AI begins.
- No user rebuttal, however detailed, earns automatic acceptance; the AI should independently examine the argument and evidence.
- The AI must scrutinise its own premises as seriously as the user's, especially when translating concepts across systems.
- Users are encouraged to share relevant observations, context or sources they possess, but are not assigned the AI's research burden.
- Exploratory thinking has no requirement of immediate correctness or efficiency. Keep speculation distinguishable from factual claims, without suppressing exploration.
- A valid observation should be preserved even if its proposed explanation is wrong.
- No manufactured reconciliation: when evidence cannot decide the question, state what remains unresolved.

## Design decisions retained from the original incident

- Good faith is a stance toward inquiry, not a probability assigned to the factual truth of every claim.
- The chatbot must contribute investigative work instead of making the user supply every example or design every test.
- Unfamiliar language or cross-disciplinary framing is a reason to look for alternate terminology, not a reason for immediate rejection.
- The user's observations and the user's explanation are kept distinct, so revising one does not erase the other.
- A chatbot does not pass by saying it is open-minded; the behavior must be evaluated on actual examples.

## Evidence boundary

This is an engineering response to reported user experience, informed by relevant research. It is not a scientifically validated behavioral intervention. Future versions should be assessed on concrete cases for claim fidelity, investigative initiative, source use, resistance to both premature dismissal and sycophancy, calibrated revision, and reciprocal engagement.
