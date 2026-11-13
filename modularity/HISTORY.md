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
