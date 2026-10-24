# History: How Automaticity Emerged

This history records the path from the user's initial question about reading to the `automaticity` AI skill. It is a project history, not a claim that the user discovered automaticity as a scientific phenomenon. It is reconstructed from available conversation records; it does not pretend to be a verbatim transcript of every exchange.

## 6 October 2026 — The starting observation: reading can become work

The investigation began with a question about the brain's “fallback in reading standard.” The user was reacting to the extra work imposed by *professor-speak*: an answer could contain a useful idea yet make the reader spend attention decoding its wording before getting to think about the idea itself.

A grade-level comparison came up as a way to illustrate differences in reading difficulty, but the user clarified that grade level was not the target. The question was about the processing work demanded by the language, not about assigning a reader a grade or making every answer simplistic.

The user then connected reading to motor learning. Practised actions can become automatic; a person can learn newer skills while older routines remain available as a fallback. The user's game-controller analogy helped express the idea: once a routine is practised, it may no longer need the same deliberate attention it needed while being learned. The user proposed that language, being a learned skill too, might have comparable layers of automaticity, effort, and fallback.

This was the conceptual starting point for the skill: familiar words and ordinary sentence patterns may be processed more automatically, while unfamiliar wording or demanding constructions can make reading effortful. The practical concern was that unnecessary effort spent decoding an answer can compete with the attention needed to reason about it.

## The first research questions — Reading, ageing, and the brain

The user next asked about Alzheimer's disease and diminishing reading and writing capacity. This was a question to investigate, not an assumption that reading necessarily survives intact as other abilities decline. The underlying interest was whether practised components of reading might behave differently from other parts of reading and comprehension as abilities change.

The user then asked for EEG and fMRI research involving people reading prose at different levels of difficulty. The aim was to look for evidence about the brain's processing demands, rather than rely only on subjective impressions that one passage feels harder than another.

These questions established the project's research direction: examine what is known about automatic and effortful reading, the demands created by words and sentence structure, and what changes when reading becomes difficult. The research should inform the design, but it should not be used to present the eventual AI skill as already scientifically validated.

## From the reading question to an AI response intervention

The application followed from the original problem with AI answers: the same idea can be expressed in language that either helps a reader get to the idea or makes the reader work through avoidable linguistic friction first.

The design goal was therefore not merely to make writing sound friendly, casual, or “simple.” It was to change the *form* of the explanation while retaining its substance. Grade level was not a universal target, and short sentences were not treated as automatically better. The relevant question was whether the wording and structure made the idea easier to process without removing any of the idea.

A proposed research comparison was to have people read answers from different AI systems that conveyed equivalent meaning, then examine whether differences in wording and sentence structure were associated with differences in neural workload. This was a proposed experiment, not a completed study.

## 7 October 2026 — Turning the idea into a reusable skill

The user took the idea to Claude and asked for a reusable skill file and a research README. The intended artifact was an AI-use skill grounded in a research rationale, not a personality preset or a request to flatten every answer to a particular reading grade.

The guiding rule became:

> **Simplify the form. Never simplify the idea.**

The operational approach is to prefer common words, shorter and more direct sentences, one main idea at a time, concrete examples before abstractions where useful, and plain explanations of technical terms. It also asks the writer to preserve the full conceptual content and check whether a reader would need to reread unnecessarily. These are design instructions to test, not proof that every listed technique reduces cognitive load for every reader.

The research document and the skill file serve different purposes:

- `automaticity/README.md` records the rationale, relevant research, references, and limits of the claims.
- `automaticity/SKILL.md` turns the proposed approach into instructions an AI agent can follow.

## 12 October 2026 — Recovering the project and preparing to publish

The user brought the existing research README and skill file back into the current workflow and decided to give the project a public, citable home. The intended sequence is to prepare a GitHub repository, add a page to the existing Memory Prism website, and then archive a version in Zenodo.

The user explicitly asked to review the history before anything was pushed. The repository was then simplified to keep each skill self-contained: one folder, with its `HISTORY.md`, `README.md`, and `SKILL.md`. The current skill is named `automaticity`, without prematurely narrowing it to “writing.” No publication step should be inferred from this history draft.

## Evidence boundary

This history distinguishes three things:

1. **The user's starting observation and hypothesis:** language can impose avoidable processing work, and practiced reading routines may become automatic in ways that make the motor-skill analogy useful.
2. **The research questions:** what neuroscience and reading research says about automaticity, text difficulty, neural workload, and reading/writing changes associated with Alzheimer's disease.
3. **The engineering proposal:** an AI skill designed to reduce unnecessary friction while preserving meaning.

The first motivated the second; the second informs the third. That sequence does not establish that the proposed skill has already been tested experimentally or that it improves comprehension, reasoning, or neural efficiency. Those remain claims to evaluate rather than conclusions to announce.


## 15 October 2026 — Applying object promotion to written communication

The user identified a new application for the existing `automaticity` skill: use bold and italics selectively to help promote relevant objects and ideas in text. The source is Making Vision, especially its distinction between background, candidate, and promoted candidate/event.

The update is not a blanket instruction to add emphasis. It asks what deserves further processing in context. The target may be an object, a changed state, an event, an action, a relationship, or a consequence; it need not be the noun naming an object. Promotion does not imply full identification, and novelty does not guarantee promotion.

Bold and italics are treated as possible interface cues, not as biological mechanisms or proven equivalents of visual promotion. Their effect on scanning and comprehension remains an engineering hypothesis. ALL-CAPS is not treated as a neutral alternative because online capitalization can also signal shouting, anger, insistence, or rudeness. The update therefore calls for contextual interpretation and selective use rather than a universal typography rule.

Source links:
- Making Vision reading page: https://www.memoryprism.com/readings/making-vision
- Zenodo record 22672458: https://zenodo.org/records/22672458

## 24 October 2026 — Connecting Automaticity to research on AI-generated language

The user brought a recent preprint, *Why Is AI-Generated Language So Hard to Understand?* by Clark, Martin, and Mahowald (2026), into the project. The paper examines linguistic patterns in outputs from nine AI models and reports a controlled experiment in which a response-length penalty shifted grammatical choices in a small model.

The connection is not that the paper validates Automaticity. Rather, it offers a plausible mechanism for the problem the skill targets: optimisation for task performance or token economy can favour forms that are less comfortable for human readers. The project therefore distinguishes **compression** from **communicative efficiency**.

The research rationale and evidence limits were added to `README.md`; a short operational caution was added to `SKILL.md`; and this history records the change. The proposed next evaluation is a meaning-matched comparison of ordinary model prose and Automaticity-style prose, measuring comprehension, reading time, recall, and preservation of substantive information.

Reference:
- Clark, T. H., Martin, M. B., & Mahowald, K. (2026). *Why Is AI-Generated Language So Hard to Understand?* https://arxiv.org/abs/2610.29162

Evidence boundary: the preprint does not test this skill directly. The application remains an engineering hypothesis.
