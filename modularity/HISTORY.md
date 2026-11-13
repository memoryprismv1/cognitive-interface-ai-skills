# History: Modularity

This history records the development of Modularity as a general-purpose planning capability. The user's examples and corrections are retained as design observations, not presented as independent scientific evidence.

## 13 November 2026 — Initial problem statement

The user identified a recurring AI failure: an agent receives a substantial objective and turns it into one oversized workflow. The resulting execution is vulnerable to context growth, token exhaustion, timeouts, loss of intermediate state, and unnecessary repetition. In software work, this can also appear as unrelated tasks being placed in one branch.

The initial research discussion covered hierarchical planning, task-decoupled planning, context management, and durable execution. The first framing was too quick to treat the solution as task decomposition plus execution estimates.

## 13 November 2026 — User correction: blockers and foundations come first

The user clarified that the first planning question is not always which execution modules to create or how long they will take. The agent must first identify blockers and foundational work.

The user used children's construction play as an analogy: before building a sandcastle or LEGO structure, children establish the conditions for the activity. This prompted research into loose-parts play, construction activity, resource affordances, and the role of materials in shaping exploration.

The architectural correction was significant: **base modules precede the planning of dependent execution work.**

Base modules are collections, not necessarily individual tasks. They can contain resources, information, tools, configuration, access, specifications, shared interfaces, or other prerequisites. Each collection may have internal ordering and dependencies of its own.

## 13 November 2026 — Planning model widened beyond a strict preparation phase

The user confirmed the direction and asked for research that would help ChatGPT organise tasks better rather than putting everything into one branch.

The investigation was widened to:
- loose-parts and construction play as a source of questions about resources and activity;
- Hierarchical Task Network planning for compound tasks, primitive actions, and partial ordering;
- Work Breakdown Structures for deliverable completeness;
- resource-constrained project scheduling for precedence and limited resources;
- distributed cognition for persistent external artefacts and coordinated work;
- asynchronous software-engineering agents for isolated workspaces, dependency-aware delegation, and integration;
- long-horizon context management for oversight and resumable state.

The child-play analogy remains an inspiration for the design, not proof that children use formal dependency graphs or project-management processes.

## Design decisions

- Start with the objective and environment, not an arbitrary task list.
- Identify blockers and prerequisites before planning the visible execution work.
- Build base modules as coherent prerequisite collections.
- Record the contents, internal order, dependencies, and readiness criteria for each base module.
- Do not impose a rigid global gate: a work package can start when its own required foundations are ready, even while unrelated base modules are still being prepared.
- Decompose the objective into deliverable-oriented work packages.
- Keep the deliverable hierarchy distinct from the dependency graph and schedule.
- Estimate consumption for base modules as well as execution work packages.
- Use ranges, assumptions, confidence, and unknowns rather than false precision.
- Choose branches and workspaces around coupling, shared files, stable interfaces, independence, and integration costs—not one branch per task.
- Persist meaningful progress and resume points where infrastructure permits.
- Let execution findings revise the base-module map and downstream plan.
- Avoid heavyweight planning for simple work.
- Coordinate with Task Integrity, Context Course Correction, Verification Integrity, Optionality, and Software Literacy rather than duplicating their responsibilities.

## Evidence boundary

Research on loose-parts play supports the finding that open-ended materials can affect children's observed exploration and construction behaviours. HTN planning, WBS, resource-constrained scheduling, distributed cognition, and asynchronous software-engineering research support distinct planning concepts.

None of these sources validates this exact Modularity skill. Whether the proposed procedure reduces monolithic execution, improves branch allocation, lowers token consumption, prevents timeouts, or improves task success remains to be tested.

## Initial test plan

Three initial evaluation cases were created:
1. A multi-part software objective with shared interfaces and partially independent deliverables.
2. A task with prerequisite collections that have their own internal ordering and readiness conditions.
3. A task where over-fragmentation would create unnecessary branches and coordination cost.

These are test specifications, not completed experimental runs. Results must be recorded separately after actual evaluation.


## 13 November 2026 — User correction: context exhaustion should end at a checkpoint

The user clarified the central operational objective: context will always run out, and Modularity should arrange for it to run out at a checkpoint. The goal is not to prevent context exhaustion or keep a conversation alive indefinitely. It is to make conversation termination harmless to completed work and recoverable for unfinished work.

This changes the emphasis from generic task decomposition and recovery planning to **checkpoint-driven execution across a finite context lifecycle**.

Design implications:
- Define safe stopping points before execution, not after interruption.
- Reserve capacity for verification, state recording, and persistence.
- Stop starting substantial work when there is not enough capacity to reach its next safe checkpoint.
- Treat conversation/session boundaries as distinct from work-package, branch, and module boundaries.
- Distinguish completed and verified work from incomplete-but-recoverable work and pending/blocked work.
- A checkpoint must include durable output references, verification evidence, current partial state, decisions, dependencies, blockers, next action, and work that must not be repeated.
- A chat summary alone is not durable persistence. Verify the saved checkpoint where storage is available; otherwise disclose that only a conversational handoff was produced.
- Resume from the latest verified checkpoint and avoid repeating completed discovery or implementation without new evidence.

## 13 November 2026 — Evaluation clarification

The three original test specifications were retrieved and reviewed. Earlier simulations in the conversation used improvised scenarios and did not follow the full contents of the original specifications; their scores should not be treated as evaluation results for the specified test suite.

Subsequent simulations were reframed around safe stopping points for the three original test themes:
1. Multi-part software delivery with shared interfaces and partially independent deliverables.
2. Ordered prerequisite collections with local readiness and partial progress.
3. Branch boundaries that avoid both monolithic workspaces and over-fragmentation.

These simulations demonstrated plausible checkpoint plans, but did not execute repository work, persist checkpoint artefacts, terminate a conversation, or resume in a separate session. They are design exercises, not empirical evidence of cross-session recovery or reduced context loss.

A future evaluation should force an interruption at a defined checkpoint, provide a fresh session only the persisted handoff and necessary artefacts, and measure whether it resumes accurately without repeating completed work. It should also test an interruption during incomplete work and verify that the checkpoint does not misrepresent partial work as complete.

The empirical status remains open: whether checkpoint-driven execution reduces lost work, repeated effort, context-related failures, or total resource consumption must be measured in actual runs.
