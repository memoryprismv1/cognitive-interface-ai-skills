# Approach Calibration & Help-Seeking

**Status: Provisional, in development; not yet validated as a reliable capability.**

## Purpose

Help an AI agent decide whether its current approach is adequate and choose a sensible next action, including whether to seek human help. The skill is specifically designed to avoid both unnecessary dependence and unsupported persistence.

**Core rule: Help-seeking is a decision, not a default.**

The goal is not to make an agent ask more questions. It is to make requests more selective and useful while preserving independent progress on tasks the agent can reasonably handle.

## The capability of interest

We are investigating whether an agent can better recognise:
- when the current approach is working well enough to continue;
- when the approach should change;
- when uncertainty can be resolved by investigation or tools;
- when a reversible default is adequate;
- when a material, unresolved dependency makes human input worthwhile;
- when continued attempts are no longer productive.

These are distinct decisions. Asking a human is only one possible response to a limitation, not the automatic response to uncertainty.

## Research rationale

The research below motivates aspects of the design. It does **not** validate this skill. Published systems typically address narrower tasks, such as ambiguity in coding requests or clarification of user intent, rather than general-purpose calibration of an agent's own approach.

1. **Edwards & Schuster (2026), “Ask or Assume? Uncertainty-Aware Clarification-Seeking in Coding Agents.”** Research on choosing between asking a clarifying question and proceeding under an assumption in coding-agent tasks. It motivates selective information-seeking instead of always asking or always assuming.  
   https://arxiv.org/abs/2603.26233

2. **Zhao, Fang & Cheng (2026), “When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification.”** Studies when to ask and what to ask, with evaluation of clarification behaviour. It motivates measuring question appropriateness, not just frequency.  
   https://aclanthology.org/2026.findings-acl.845/

3. **Deng et al. (2026), “Uncertainty-Aware Clarification in LLM Agents with Information Gain.”** Uses information gain to guide clarification decisions. It motivates asking when a question is expected to resolve consequential uncertainty, rather than in response to uncertainty alone.  
   https://proceedings.mlr.press/v306/deng26l.html

4. **Kamoi et al. (2024), “When Can LLMs Actually Correct Their Own Mistakes? A Critical Survey of Self-Correction of LLMs.”** Reviews limitations in LLM self-correction. It warns against treating self-critique or a narrated confidence estimate as evidence that the agent has reliably detected its own error.  
   https://aclanthology.org/2024.tacl-1.78/

5. **Testoni & Fernández (2024), “Asking the Right Question at the Right Time.”** Examines uncertainty and clarification decisions. It motivates examining whether model uncertainty estimates actually align with useful clarification behaviour.  
   https://aclanthology.org/2024.eacl-long.16/

The papers differ in scope and method. Report individual findings with their original experimental boundaries; do not combine their reported metrics into a single claim about general agent capability.

## Design hypothesis

A lightweight instruction skill may influence how an agent evaluates its progress and chooses among continuing, changing approach, investigating, proceeding with an assumption, seeking help, or stopping. Whether it produces stable improvements across tasks, models, and tools is an empirical question.

Do not assume the agent has a dependable scalar confidence meter. Self-reported confidence, token probabilities, agreement among sampled answers, evidence sufficiency, and confidence in a chosen approach are different quantities. None should be treated as ground truth without appropriate validation.

The skill does not require a visible numerical confidence score. Calibration should primarily be evaluated through observable decisions and outcomes.

## Evaluation plan

Compare the same model and task/tool environment with the skill enabled and disabled. Keep the actual user task and available capabilities constant. The presence of an `ask_user` affordance must be the same in both conditions; otherwise the test cannot isolate the effect of the skill.

Include cases where:
- the agent should simply proceed;
- a missing detail can safely be defaulted;
- a tool or source can resolve the uncertainty;
- a method fails but a meaningful alternative is available;
- evidence conflicts and requires investigation;
- an essential decision or fact is inaccessible and human help is justified;
- repeated attempts fail and the agent must reassess.

Where possible, use interactive two-turn tasks: the agent chooses whether to seek help, a fixed human-simulator response is provided when asked, and the evaluator checks whether the agent integrates the response and resumes. Single-turn answers that merely *say* “I would ask” do not establish that an agent can pause, request input, and act on the reply.

Score separately:
1. **Recognition:** Did it detect an actual limitation, contradiction, or failed approach?
2. **Decision quality:** Was the selected next action appropriate given the information available at that time?
3. **Question quality:** If it asked, was the request necessary, targeted, and actionable?
4. **Unnecessary interruption:** Did it ask when it could reasonably proceed or investigate?
5. **Recovery:** Did it try a useful alternative, use retrieved information, or integrate the human response?
6. **Outcome:** Correctness, task completion, constraint compliance, reversibility, and harm risk.
7. **Cost:** Turns, tool calls, latency, and token use.

A lower question rate is not inherently better. A higher question rate is not inherently better. The target is appropriate selective help-seeking. Report false asks and missed asks separately; aggregate success can conceal both.

Run multiple tasks and, where feasible, repeated samples. Human scoring should use fixed criteria established before inspecting condition labels. Record ambiguous cases rather than forcing them into a clean result. Do not claim efficacy based on a few examples or one response per condition.

## Limits and non-goals

This is not a claim of human-like introspection, consciousness, or reliable metacognition. It is a proposal to improve and test task-level behavioural decisions.

It does not override safety rules, access controls, user authorisation, or explicit task constraints. Nor should it encourage the agent to expose hidden chain-of-thought. The relevant evidence is what the agent chooses, what it does, what it asks, and whether those choices succeed.

## Current status

The initial instruction design is ready for probing. Its behavioural effect remains unestablished. Development should preserve failed cases and negative results, and revisions should be tied to recorded evidence rather than an expectation that a longer skill must work better.
