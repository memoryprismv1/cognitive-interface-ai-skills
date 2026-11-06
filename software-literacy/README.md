# Software Literacy for AI Collaboration

**Skill:** `software-literacy`

**Purpose:** Help people without a software-engineering background participate intelligently in AI-assisted software work. The aim is not to turn every user into a programmer. It is to make software concepts, AI-generated work, risks, and choices understandable enough for people to direct the work and make informed decisions.

**Core principle:**

> **The human should be able to make an informed decision even when they do not understand the implementation.**

## 1. The problem

AI tools have lowered the effort required to generate code and assemble software. They have not removed the need to understand what that software does, how its parts depend on one another, what can go wrong, or how to establish whether it is fit for purpose.

This creates several related but distinct risks:

- AI-generated code may contain defects, security weaknesses, unnecessary complexity, or maintenance problems.
- People without software backgrounds may be able to produce or run an application without understanding its internal structure or limitations.
- A fluent AI explanation can sound authoritative while being incomplete or wrong.
- "It runs" can be mistaken for "it works correctly," "it is safe," or "it is ready for real users."
- Users may approve consequential technical choices without understanding the implications, or delegate decisions that should remain theirs.
- Verification can become a bottleneck: generation is cheap, while understanding, testing, review, maintenance, and accountability still take effort.

These claims must not be collapsed into one sweeping statement. Studies differ in population, task, code source, evaluation method, and what they call a defect or comprehension. The research must report those details rather than treating every finding as evidence about all non-software users.

## 2. What this skill is—and is not

This is **software literacy for AI collaboration**, not a programming course and not a test of whether someone is qualified to use AI.

The skill helps the AI:
- explain actual technical terms in ordinary language;
- introduce concepts when they become relevant;
- explain what it proposes to change and what else may be affected;
- distinguish generation, execution, testing, and verification;
- make choices, trade-offs, assumptions, and reversibility visible;
- recognise when a decision belongs to the human;
- help the person build a practical mental model over time.

It does not:
- assume every user wants to become a programmer;
- hide technical terminology or replace it with inaccurate analogies;
- overwhelm the user with a software textbook;
- require approval for every routine implementation step;
- treat a successful demo or passing test as proof of overall correctness;
- patronise people who are unfamiliar with software.

## 3. The user's prior work and intellectual foundation

This skill is being developed within the user's existing Memory Prism work. The user's published essays are part of the project's intellectual foundation and must retain their provenance. They are not decorative references added after the external research.

### The Intern Who Never Sleeps

[The Intern Who Never Sleeps — Memory Prism](https://www.memoryprism.com/positions/ai-intern-monkeys)

The essay identifies a growing mismatch between the rate at which AI can generate work and the human capacity to examine it. Its central concern is not simply whether AI can produce output, but whether people and institutions can meaningfully verify what has been produced when generation continues faster than review.

### AEL and AI

[AEL and AI — Memory Prism](https://www.memoryprism.com/positions/ael-and-ai)

The essay frames a central AI risk as **capability without consequence**. It develops the idea that systems need to account for the consequences of actions rather than merely execute an objective. This is directly relevant when an AI proposes software changes whose effects extend beyond the immediate task.

### Vive et Vivere Sinas

[Vive et Vivere Sinas — Memory Prism](https://www.memoryprism.com/essays/signal-and-cost/vive-et-vivere-sinas)

This essay develops consequence literacy as part of the way systems learn to persist and coexist. It connects education with the updating of consequence maps as conditions change. This skill applies that educational idea to the changing technical environment created by AI-assisted software work.

These works supply the user's prior observations, conceptual framing, and arguments. External studies may support, challenge, or independently converge with them; those studies must not be presented as the origin of the user's ideas. The skill operationalises parts of this prior work for a particular setting: people making decisions about software with AI assistance.

## 4. Research directions

The research base should be built in distinct strands. Each paper must be assessed for its actual population, task, method, measured outcome, and limitations.

### A. AI-generated code quality and software risk

Investigate empirical work on:
- functional defects and code quality;
- security vulnerabilities;
- code smells and maintainability;
- technical debt and downstream repair;
- differences between benchmark-generated code and code used in real repositories.

A study finding issues in AI-authored commits does not by itself tell us how often non-software users deploy defective applications. It supports the need for quality controls, not every claim about users.

### B. Novice and non-specialist use of AI coding tools

Investigate work involving:
- people from non-computing disciplines;
- citizen developers and no-code/low-code users;
- novice programmers using code-generation tools;
- people who build applications with AI without being able to reproduce, explain, debug, or maintain them independently.

Record whether a study examines actual non-software professionals, computing students, classroom exercises, or self-selected survey respondents. Do not treat these populations as interchangeable. This strand is especially important and remains an evidence gap in the initial source set below.

### C. Comprehension, cognitive offloading, and automation bias

Investigate:
- whether AI assistance changes learning and retention;
- whether users can explain or debug AI-generated output;
- reliance on fluent or confident AI explanations;
- how users decide when to check AI output;
- whether interface design and explanation quality improve appropriate reliance.

Distinguish reduced effort from loss of understanding. Cognitive offloading can be useful; the relevant question is whether users retain enough understanding and oversight for the task.

### D. Verification and human oversight

Investigate:
- code review and testing practices;
- test coverage and limits of passing tests;
- security review and threat modelling for novice builders;
- human oversight of automated systems;
- practical ways to communicate uncertainty, risk, and decision authority.

## 5. Initial research foundation

The following sources have been located and inspected as initial research anchors. The list is not a systematic review and does not establish the effectiveness of this skill.

### AI-generated code quality

**Liu, Y., Widyasari, R., Zhao, Y., Irsan, I. C., Chen, J., & Lo, D. (2026).** [Debt Behind the AI Boom: A Large-Scale Empirical Study of AI-Generated Code in the Wild](https://arxiv.org/abs/2603.28592). arXiv:2603.28592, version 3 (13 October 2026).

The authors analyse 302,600 verified AI-authored commits from 6,299 GitHub repositories. Their static-analysis method attributes 484,366 issues to those commits; 89.3% are classified as code smells, and 22.7% of tracked issues remain in the latest repository revision examined. This is evidence about AI-authored changes in sampled repositories, not a direct estimate of defects in applications built by non-specialists. The categories are derived from static analysis and should not all be described as runtime bugs.

**Cotroneo, D., Improta, C., & Liguori, P. (2025).** [Human-Written vs. AI-Generated Code: A Large-Scale Study of Defects, Vulnerabilities, and Complexity](https://arxiv.org/abs/2508.21634). arXiv preprint.

The study compares more than 500,000 code samples in Python and Java. It reports different defect profiles for AI- and human-written code, including more high-risk security vulnerabilities in the AI-generated sample, while also reporting differences in complexity and maintainability indicators. This is a preprint study under specific evaluation conditions, not proof that AI code is categorically worse in every language or context.

**Schreiber, M., & Tippe, P. (2025).** [Security Vulnerabilities in AI-Generated Code: A Large-Scale Analysis of Public GitHub Repositories](https://arxiv.org/abs/2510.26103). arXiv preprint.

The authors examine 7,703 files attributed to four AI coding tools and report 4,241 CWE instances across 77 vulnerability types. The analysis also reports that 87.9% of the sampled AI-generated code did not contain identifiable CWE-mapped vulnerabilities. The study illustrates why both the denominator and the method matter: it identifies risks in a particular repository sample and should not be paraphrased as "most AI code is insecure."

### Comprehension and code ownership

**Shen, J. H., & Tamkin, A. (2026).** [How AI assistance impacts the formation of coding skills](https://www.anthropic.com/research/AI-assistance-coding-skills). Anthropic research report; paper cited as arXiv:2601.20245.

This randomized controlled trial involved 52 mostly junior software engineers who already used Python regularly. Participants learning the Trio Python library with AI assistance scored an average of 50% on a post-task quiz, compared with 67% for the group coding without AI. The study focused on developers learning a new programming library; it does not directly study people with no software background. The authors also report that AI use was not uniform: participants who used it to seek explanations and conceptual understanding showed stronger mastery.

**(2026).** [More Code, Less Understanding? On the Impact of AI Assistants on Developers' Productivity and Code Ownership](https://ieeexplore.ieee.org/document/11458664/). *IEEE Transactions on Software Engineering*, 52(7), 2173–2187. DOI: 10.1109/TSE.2026.3679627.

An experiment with 69 participants (including bachelor's and master's students, researchers, and professional developers) compared two code-writing tasks with and without AI assistance. The authors report higher task completeness with AI, alongside a 12.5% reduction in participants' ability to answer technical questions about the code they had implemented, used as a proxy for code ownership. The mixed sample and task design must be considered when interpreting the result; it is not a direct study of non-programmers.

### Current evidence gap

The initial research anchors show that generated code can introduce quality issues and that AI-assisted coding can be associated with weaker immediate understanding or code ownership in some developer populations. They do **not** yet adequately establish what happens when people with little or no software experience build and use real applications with AI agents.

That population and context should be a deliberate target for further research, not silently filled in by generalising from professional developers or computing students.

## 6. Design rationale

The proposed intervention is a combination of practical software education and better AI communication.

The AI should not merely answer a question in plain language. It should help the person understand enough of the system to recognise what is being built, what a change means, which choices matter, and what evidence would support confidence.

A useful progression is:

1. **Orient:** identify the user's goal and relevant parts of the system.
2. **Explain:** introduce the real concepts and vocabulary needed for the task.
3. **Expose choices:** explain alternatives, consequences, assumptions, and reversibility.
4. **Act:** implement within the agreed scope, without needless approval loops.
5. **Check:** test the relevant behaviour and explain what the checks do and do not establish.
6. **Transfer:** help the user recognise the same concepts and decisions in future work.

This is a flexible design model, not a mandatory six-step ceremony for every interaction.

## 7. Evaluation plan

Test whether the skill changes observable interaction and user understanding. Compare the skill enabled and disabled under similar tasks and conditions where feasible.

Potential measures:
- ability to explain the purpose and major parts of the resulting system;
- ability to identify consequential changes and likely affected components;
- ability to distinguish "runs," "tested," and "verified";
- recognition of missing evidence and unsupported AI claims;
- quality of decisions about security, data, cost, maintenance, and deployment;
- ability to ask useful questions and challenge unsupported proposals;
- task completion, defects, and rework;
- cognitive burden, unnecessary interruptions, and user confidence calibrated against actual understanding.

Do not equate self-reported confidence with comprehension. Use scenario questions, teach-back, choice explanations, and practical tasks. Include both people with no coding experience and people with some technical experience, and report the groups separately.

Test whether the AI's explanations are accurate as well as understandable. An accessible false explanation is still a failure.

## 8. Evidence boundary

This is a proposed AI interaction and learning intervention. Existing studies can establish particular facts about code quality, novice use, learning, trust, or verification. They do not establish that this complete skill improves software outcomes or user comprehension.

Keep these categories separate:
- the user's original observations and published arguments;
- findings directly measured by external research;
- interpretations that connect findings to this problem;
- proposed AI behaviours;
- outcomes that require direct evaluation.

A study of students is not automatically evidence about working professionals. A study of novice programmers is not automatically evidence about people who have never programmed. A code-quality benchmark is not a deployment audit. A self-report is not a direct comprehension measure.

The purpose is informed participation, not professional certification. The user remains entitled to direct the work and make decisions without learning to implement every technical detail.

## Status

**Status:** Initial design. Research foundation and evaluation remain in development.

**Core principle:**

> **Understand what AI builds. Understand what you're deciding. Stay in control.**
