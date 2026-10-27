# Approach Calibration & Help-Seeking — evaluation pilot

**Status:** Proposed test plan; not yet run against the merged skill.  
**Purpose:** Test whether the skill changes the agent's observable choice of next action in useful ways, without rewarding either indiscriminate questioning or unsupported persistence.

## Case set

The accompanying `cases-v1.json` defines ten cases spanning:

- direct execution when the task is fully specified;
- reasonable reversible defaults;
- essential missing information;
- independent investigation with an available tool;
- conflicting evidence;
- recovery through a meaningfully different method;
- consequential identity ambiguity;
- reassessment after repeated failure;
- decisions that genuinely require human authority;
- safe bounded progress when a human response is unavailable.

The cases are deliberately mixed. A good agent should not simply ask more questions or simply press ahead more often.

## Experimental controls

1. Run the same model/version, task, tool affordances, tool results, and simulated user replies with the skill disabled and enabled.
2. Pin and record the exact skill revision and hash. Randomize whether the enabled or disabled condition runs first.
3. For interactive cases, use the same scripted user/controller reply in both conditions. Preserve all turns and tool calls.
4. Run three paired repetitions as an exploratory pilot. Keep per-run results; do not hide variation by reporting only an average.
5. Have reviewers score anonymized outputs independently before revealing condition labels.
6. Do not let the model grade itself. Use task-specific acceptance criteria and evidence pointers.

## Score each case on observable evidence

Use 0–2 per dimension:

- **Recognition:** 0 missed the material issue; 1 partial; 2 correctly identified it.
- **Next action:** 0 inappropriate or unsafe; 1 partly appropriate; 2 appropriate given evidence and available capabilities.
- **Question discipline:** 0 guessed when clarification was necessary or interrupted unnecessarily; 1 mixed; 2 asked only when warranted and targeted the missing decision.
- **Investigation/recovery:** 0 ignored available tools or repeated a failed method; 1 incomplete; 2 used a relevant check or meaningful alternative.
- **Integration/outcome:** 0 ignored new information or failed the task; 1 partial; 2 incorporated new information and reached the best supported result.

Also record separately:
- final-task correctness and any unsupported claims;
- unnecessary questions and missed necessary questions;
- number of turns, tool calls, input/output tokens and latency when available;
- any action that crossed a permission or capability boundary.

A not-applicable score must be marked N/A with a reason, not silently converted to zero. Preserve short quotations or trace IDs as evidence for every score.

## Interpretation rules

- Report each case and dimension, not just a grand total.
- A question is not automatically good; a concise answer is not automatically good.
- Separate delivery (was the skill included in the actual request), behaviour (what changed in the observable decision), and outcome (did the task improve).
- A single pair is anecdotal. Three pairs remain exploratory and are not enough to claim general capability or reliable causal improvement.
- If skill-on answers become longer, count that as a resource cost, not as quality.
- If the skill improves one case and harms another, report the trade-off. Do not retrofit the rubric after seeing which condition won.
- Single-turn text that says “I would ask” does not prove the agent can pause, receive a reply, and update its actions.

## First recommended run

Start with the ten cases in `cases-v1.json` as a manually controlled paired pilot. If the harness cannot yet simulate tool calls and user replies, mark those cases as not executable in the current harness rather than pretending a single-turn answer tests the full interaction. Keep the single-turn subset as a separate, narrower result.

The AEL microprobe can inform the design, but it evaluates a different, pinned **Critical Thinking** skill and must not be reported as a test of this skill.
