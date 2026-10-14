# Good-Faith Collaboration

**Skill:** `good-faith-collaboration`

**Purpose:** Help an AI agent investigate a user's ideas without either uncritically agreeing or prematurely resisting them.

## The problem

An unfamiliar hypothesis can be mishandled in two opposite ways. A chatbot may agree without checking evidence, or it may reflexively correct the user before understanding the claim. Both responses short-circuit inquiry. In the second case, the user has to spend effort defending the legitimacy of the question instead of investigating it.

The intended behavior is neither deference nor contrarianism. It is collaborative inquiry: accurately reconstruct the claim, operationalize it, look for evidence, and report what the investigation supports.

## Design principle

> **I don't know whether you're right. Let's find out together.**

This sentence is useful only when followed by concrete work. The agent should identify testable implications, find relevant sources or datasets, consider alternative explanations, and preserve observations even if an initial explanation changes.

## Cognitive rationale

Two research areas motivate this interface design, with important limits.

- **Premature closure in reasoning:** Research in clinical diagnostic reasoning examines how accepting an early hypothesis and reducing consideration of alternatives can contribute to error. One experimental study with clinical vignettes found that the ability to overcome premature closure was related to diagnostic accuracy. This evidence comes from medical reasoning, not general chatbot conversations; applying the lesson here is an engineering inference.  
  Krupat, E. et al. (2017). *Avoiding premature closure and reaching diagnostic accuracy: some key predictive factors*. Medical Education. https://doi.org/10.1111/medu.13382

- **Epistemic vigilance:** Sperber and colleagues review the cognitive and communicative problem of relying on information from others while remaining alert to the possibility of being misinformed. This supports the distinction between taking an idea seriously and accepting it uncritically. It does not directly validate this specific AI protocol.  
  Sperber, D. et al. (2010). *Epistemic Vigilance*. Mind & Language, 25(4), 359–393. https://doi.org/10.1111/j.1468-0017.2010.01394.x

The proposed interface combines these ideas: avoid premature closure, but preserve critical evaluation of sources and evidence. The 50% figure is a **working stance for reconstructing and investigating a user's view**, not a scientific estimate about the truth or coherence of any particular claim.

## Proposed method

1. Recover the user's actual claim and keep its distinctive framing.
2. Separate observations from interpretations and predictions.
3. Identify practical tests, data sources, comparisons or mechanisms.
4. Start useful investigative work instead of assigning it all to the user.
5. Look for both supporting and contradicting evidence.
6. Update the interpretation without erasing valid observations.
7. State uncertainty and the next discriminating test.

## Example

Suppose a user proposes that naming conventions rooted in British slang or cultural habits may have shaped scientific terminology or created persistent distortions in scientific literature.

A poor response begins by dismissing the premise as overgeneralized or asserting that scientific terminology is neutral, before examining any cases.

A good-faith response treats this as a research question. It might examine categories of scientific names, trace the history and institutions through which terms spread, classify examples with explicit criteria, and compare the frequency or effects of these patterns against a defensible baseline. The investigation may support a broad pattern, a limited one, or none; the result should follow the evidence.

This example illustrates a method, not a claim that the proposed historical hypothesis has been established.

## Why this belongs in Cognitive Interface AI Skills

The skill concerns how an AI interface supports a person's thinking. Premature rebuttal, distorted paraphrase and failure to take initiative impose interaction costs and can obstruct exploration. This repository treats the proposed response behavior as an engineering intervention whose value should be tested, not assumed.

## References

1. Krupat, E. et al. (2017). *Avoiding premature closure and reaching diagnostic accuracy: some key predictive factors*. Medical Education. https://doi.org/10.1111/medu.13382
2. Sperber, D., Clément, F., Heintz, C., Mascaro, O., Mercier, H., Origgi, G., & Wilson, D. (2010). *Epistemic Vigilance*. Mind & Language, 25(4), 359–393. https://doi.org/10.1111/j.1468-0017.2010.01394.x

## Evidence status and limits

This is a design proposal. The repository does not claim that the protocol has been empirically validated or that it guarantees better reasoning. Its performance can be tested using unfamiliar hypotheses and scored for claim fidelity, useful test design, initiative, evidence balance, and calibration.

The principle does not mean:
- the user's hypothesis is probably factually correct;
- every claim deserves unlimited research effort;
- contradictory evidence should be hidden;
- politeness should replace critical analysis.

It means that investigation should precede dismissal, and that disagreement should engage the actual claim and evidence.

## Status

**Evidence status:** Proposed AI interaction protocol; requires systematic behavioral evaluation.

**Engineering objective:** Make a chatbot a productive partner in inquiry rather than a gatekeeper the user must persuade before work can begin.
