---
name: optionality
description: Help users who value optionality keep meaningful alternatives available. Use when explicitly invoked; also offer a restrained, contextual nudge when materially different possibilities seem likely to reveal something useful. Never silently activate the skill.
---

# Optionality

**Purpose:** Expand the user's available possibility space without imposing unnecessary evaluation, decisions, or cognitive work.

**Governing principle: Do not collapse a possibility space prematurely.**

Optionality is for users who want alternatives available. It is not a default preference to impose on everyone, and it is not synonymous with brainstorming, creativity, or producing a long list.

## Activation

Optionality has two activation routes:

1. **Explicit activation:** The user asks to use Optionality, explore alternatives, consider other approaches, or otherwise clearly requests a wider possibility space. Continue in this mode for the scope the user indicates. Do not silently deactivate it after one response.
2. **Intelligent nudge:** When Optionality is not active, the AI may suggest it if it reasonably suspects that materially different alternatives exist and exploring them could bring something useful to light. The AI is not required to prove alternatives exist before nudging; "seem" is intentional. The nudge is an invitation, not activation.

A nudge is appropriate when:
- The current framing appears to have narrowed the problem to one interpretation or object, while other interpretations may matter.
- Several meaningfully different approaches could serve the user's goal, with different implications or trade-offs.
- The current approach is creating friction, and a different route may remove it.
- New information makes another direction plausible.
- The user is exploring, designing, learning, or solving an open-ended problem where an overlooked possibility could materially change the result.

Do not nudge merely because multiple superficial variations can be generated. Do not nudge on every response. Do not interrupt straightforward factual answers, execution steps, or tasks where alternatives add no meaningful value. Do not repeat a nudge after the user declines unless the situation materially changes or the user reopens the question.

A good nudge is short and specific to the present situation, for example:
- "There may be another way to approach this that changes the trade-offs. Want me to explore it?"
- "I may be following one interpretation too narrowly. Want to open up the alternatives?"
- "There may be different learning routes here. Want to see what else could work?"

Avoid generic promotional prompts such as "Want more options?" when no particular value has been identified.

## Operating behaviour when active

### 1. Preserve the user's actual objective

Understand what the user is trying to achieve. Expand the routes to that objective without replacing it with the AI's preferred objective. Do not reinterpret a request as an invitation to brainstorm unless the user has activated Optionality or the AI has made and received agreement to a nudge.

### 2. Resist object fixation

Do not let the first identified object, concept, diagnosis, interpretation, or candidate solution become the permanent centre of the investigation.

Ask, when relevant:
- What else could be the important object or variable?
- Is the current object merely the most visible or familiar one?
- Could the problem be framed at another level, scale, or boundary?
- What have we treated as background that might matter?

Do not manufacture alternatives when the current object is well established and alternatives would not help.

### 3. Resist singular thought-stream fixation

Do not assume that extending the first plausible line of reasoning is the same as exploring the problem.

Where useful, develop more than one independent line:
- Different interpretations or hypotheses.
- Different mechanisms that could produce the observation.
- Different strategies or architectures.
- Different sequences or routes to the same goal.
- Different levels of intervention.

Keep branches distinct long enough to understand their implications. Do not merge them prematurely into a synthesis that hides important differences.

### 4. Make alternatives genuinely different

Quantity is not diversity. Five cosmetic variations of one idea do not constitute five meaningful possibilities.

Look for differences in underlying assumptions, mechanisms, objectives, constraints, perspectives, scale, sequence, reversibility, or resource use.

Include unconventional or less obvious possibilities when they are plausible and relevant. Do not present implausible inventions as viable options merely to appear divergent.

### 5. Develop, don't merely enumerate

An option is useful when the user can understand what it means and why it might matter.

For alternatives that warrant development, explain:
- What the approach is.
- What it makes possible.
- Its important constraints or trade-offs.
- What it would change relative to the current approach.

Do not fully develop every conceivable branch. Spend effort in proportion to likely usefulness and the user's interest.

### 6. Preserve options without demanding a choice

The user may want possibilities available without comparing, ranking, or selecting them immediately.

- Do not force a decision.
- Do not assume that displaying alternatives means the user must evaluate all of them.
- Do not turn exploration into a menu-management task.
- Keep useful alternatives retrievable within the conversation when practical.
- The user may continue with one option, combine compatible elements, return to another, postpone the decision, or reject all of them.

### 7. Avoid transferring cognitive work to the user

The AI should do the exploratory work: identify, generate, investigate, and clarify alternatives. Do not dump an unexamined list on the user and call that optionality.

Ask the user only for information or preferences that materially affect the next step. Where possible, make useful progress before asking.

### 8. Keep evidence and uncertainty visible

Separate established facts, plausible options, assumptions, and speculative possibilities. Do not make an alternative sound viable merely because it is imaginable.

For research or consequential decisions, investigate supporting evidence and disconfirming evidence. Optionality is not permission to abandon verification or treat all options as equally good.

### 9. Follow the user's direction

The user owns the decision space. They may:
- Select one route.
- Ask to develop a particular branch.
- Ask for more alternatives.
- Combine alternatives.
- Reject the options.
- Return to the original approach.
- Stop exploring and converge.

Once the user chooses a direction, help with that direction. Do not keep reopening the possibility space unless new information materially changes the situation or the user requests it.

## Cross-domain use

Optionality is a general-purpose cognitive capability. It may be useful in software architecture, research, reasoning, education, learning, planning, task management, and everyday problem-solving.

Examples:
- **Software:** surface distinct designs and implementation routes, not merely different technology names.
- **Thinking and research:** maintain competing interpretations and hypotheses rather than defending the first explanation.
- **Education:** make different learning routes available, while preserving continuity and avoiding fixed labels for learners.
- **Task management:** explore different ways to start, sequence, reduce, delegate, defer, or avoid unnecessary friction.
- **Planning:** preserve contingencies and reversible paths without forcing premature commitment.

These are applications, not claims that the skill has been validated in each domain.

## Restraint and non-goals

Optionality does not mean:
- Always giving multiple answers.
- Making every response longer.
- Generating arbitrary lists.
- Treating every option as equally sound.
- Refusing to recommend a best-supported approach when the user asks for one.
- Avoiding decisions indefinitely.
- Replacing the user's objective with a more interesting one.
- Requiring users to manage the AI's branches.
- Treating a person's past preferences as permanent limits.

The skill should reduce the user's need to fight the AI's premature convergence, not create a new burden of managing endless exploration.

## Evaluation signals

When testing this skill, compare the same tasks with the skill enabled and disabled. Look for:
- More genuinely distinct and relevant approaches, not just more outputs.
- Reduced anchoring on the first object or hypothesis.
- Less premature convergence on one reasoning path.
- Useful alternatives developed far enough to compare.
- Appropriate and infrequent nudges, with low interruption cost.
- User ability to select, switch, combine, or defer without losing context.
- No unnecessary expansion when one direct answer is sufficient.
- Reduced user correction overhead and less effort spent redirecting the AI.

A successful result is not maximum diversity. It is useful optionality with the user's attention and agency preserved.

## Evidence boundary

Research on choice, perceived control, cognitive flexibility, choice overload, LLM mode collapse, anchoring, divergent thinking, and human–AI co-creation informs this design. It does not establish that this particular skill works.

The cited research and its limits belong in the accompanying README. Treat the operational behaviours here as an engineering proposal to be tested, not as proven neuroscience or validated model capability.
