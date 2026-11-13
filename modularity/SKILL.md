---
name: modularity
description: Organise substantial work before execution. Identify blockers and prerequisite foundations, assemble base modules as ordered collections, decompose deliverables into bounded work packages, map dependencies, estimate resource consumption, choose sensible execution and branch boundaries, and adapt the plan when new requirements emerge.
---

# Modularity

**Status:** Initial version; research-informed operational proposal. The complete skill has not yet been empirically validated.

**Core rule: Establish what the work needs before dividing up the work that will use it.**

## Purpose

Help an AI agent organise substantial work so that it can be executed in coherent, bounded parts without losing the original objective, omitting prerequisites, exhausting its execution environment, or making the user manage the decomposition.

Modularity is not simply splitting a task list into smaller tasks. It is the capability to discover and establish the foundations that make work possible, organise those foundations, identify what depends on what, and then form executable work packages with appropriate resource and coordination plans.

Use it for substantial software, research, analysis, data, documentation, creative-production, and operational tasks. Do not impose a planning ceremony on a simple request that can be completed directly.

## Core distinctions

### 1. Objective

The outcome the user wants. Preserve the requested scope, constraints, exclusions, quality expectations, and definition of done.

### 2. Base module

A coherent collection of prerequisites that must be available for one or more later work packages to proceed. A base module may contain resources, information, files, access, tools, environment configuration, conventions, specifications, shared interfaces, or other enabling conditions.

Base modules are collections, not automatically single executable tasks. Each collection may have:
- constituent items or sub-collections;
- an internal preparation or acquisition order;
- dependencies on other base modules;
- a completeness or readiness condition;
- a persistent location or reference;
- an owner or responsible process, where relevant.

Examples include a verified source collection, a configured development environment, an inventory of existing interfaces, a dataset with provenance, or agreed design constraints.

Do not label every preliminary action a base module. It must establish something that later work actually needs.

### 3. Work package

A bounded unit of deliverable-oriented work that produces an identifiable result. A work package may contain several tasks and can be decomposed further when that helps execution, ownership, estimation, or verification.

A work package is not automatically a Git branch, agent, conversation, or tool call.

### 4. Dependency and ordering

Containment and dependency are different relationships:
- **Contains:** a parent module groups constituent items or work packages.
- **Requires:** one item needs an output or condition from another.
- **Precedes:** one activity must occur before another.
- **Can overlap:** work may proceed concurrently once its actual prerequisites are satisfied.

Represent ordering as a dependency graph or equivalent explicit structure. Do not force unrelated work into a single sequence. Identify cycles or unresolved dependencies instead of hiding them.

## Operating procedure

These are working operations. Do not print a long checklist to the user unless they ask for it.

### 1. Understand the objective and inspect the environment

Identify:
- the desired outcome and acceptance conditions;
- explicit scope, constraints, exclusions, and decision boundaries;
- existing work, assets, files, systems, conventions, and reusable components;
- available tools, access, execution environments, and known limits;
- what is already complete, missing, uncertain, or blocked.

Inspect relevant existing project materials before inventing a new structure. Do not assume that a requested project starts from an empty environment.

### 2. Identify blockers and prerequisites before planning execution

Ask what must exist, be known, be available, or be decided before meaningful work can proceed.

Distinguish:
- hard blockers: work cannot begin without them;
- soft prerequisites: work can begin, but quality, speed, or risk changes;
- decisions: a choice or constraint is required;
- discovery tasks: the prerequisite itself is not yet understood;
- external waits: another person, service, permission, or process must respond.

Do not start by estimating the duration of the visible implementation tasks while ignoring what makes those tasks possible.

### 3. Build and order base modules

Group prerequisites into useful collections. For each base module, record:
- purpose and downstream work it enables;
- constituent resources, files, knowledge, or conditions;
- acquisition, preparation, and validation activities;
- internal ordering and dependencies on other base modules;
- completeness/readiness criteria;
- location or durable reference;
- missing items, uncertainties, and responsible owner where applicable.

A base module can itself require ordered work. For example: discover sources → retrieve sources → check access and provenance → classify coverage → declare the collection ready.

Do not require every base module in the whole project to be complete before anything can start. Readiness is assessed per dependent work package. Work may begin as soon as its own required foundation is ready, while independent foundations continue to develop.

### 4. Decompose the intended deliverables

After identifying the foundations, create a deliverable-oriented breakdown of the remaining work:
- identify major deliverables and intermediate outputs;
- group related work into coherent work packages;
- decompose only as far as needed for execution, allocation, estimation, or verification;
- make the scope of each package clear;
- check that the children account for the agreed parent scope;
- distinguish work that produces a deliverable from coordination or management activity needed to produce it.

Do not turn every verb, file, or checklist line into a separate module. Avoid both monolithic packages and arbitrary over-fragmentation.

### 5. Map dependencies and readiness

Create the dependency graph across base modules and work packages. For each package, specify:
- required predecessor outputs or conditions;
- outputs it provides to other packages;
- whether the dependency is mandatory or conditional;
- whether work is sequential, partially ordered, or independent;
- readiness status: blocked, ready, in progress, complete, or needs rework.

A task is ready only when its required inputs and conditions are available—not merely because it appears next in a numbered list.

Do not confuse the hierarchy of work with the execution schedule. A parent can contain several packages that run in parallel; a dependency can also cross branches of the hierarchy.

### 6. Estimate resource consumption

Every planned base module and execution work package must have a resource profile appropriate to its nature. Estimate after the work, boundaries, inputs, and dependencies are understood.

For base modules, consider:
- discovery and retrieval effort;
- preparation and validation effort;
- expected model tokens and peak context;
- tool/API calls and external waits;
- storage, data volume, and access requirements;
- uncertainty, rework, and readiness risk.

For execution work packages, consider:
- expected input and output tokens;
- peak working-context requirement;
- active execution time and external elapsed/wait time;
- tool/API calls;
- compute or service requirements, where relevant;
- storage and intermediate artefacts;
- retry/recovery allowance;
- verification and integration effort.

Use ranges rather than false precision. State assumptions, confidence, and major unknowns. Distinguish:
- token consumption over the task from peak context occupancy;
- active execution time from external waiting;
- per-package consumption from total project consumption;
- sequential total time from critical-path duration and parallel elapsed time;
- expected usage from a contingency or retry allowance.

If actual budgets or platform limits are known, compare estimates with them. If not known, say so and give a useful estimate without pretending to know the hidden limit. Do not invent exact token counts, runtimes, or compute costs.

### 7. Choose workspaces, branches, and execution boundaries

Choose execution boundaries after understanding the deliverables, dependencies, and coupling.

For software work:
- group tightly coupled changes that need to evolve and be tested together;
- separate work when outputs are independently reviewable, interfaces are sufficiently stable, and changes can be isolated;
- consider file overlap, shared state, schema/API coupling, integration cost, ownership, rollback, and verification;
- use a branch or worktree for a coherent work package when isolation provides value;
- reserve an integration path for combining and testing completed work.

A logical module is not automatically a branch. A base module may be a collection of research, assets, configuration, or shared prerequisites that should not become a separate branch. One branch per tiny task is usually as unhelpful as putting the whole project in one branch.

For non-software tasks, choose equivalent boundaries: separate documents, datasets, research batches, production units, or execution sessions where that improves isolation and recovery.

Do not create branches, change repositories, delegate to external agents, or modify shared infrastructure unless the user has requested the work and the available permissions permit it. Planning a branch structure is not the same as performing Git operations.

### 8. Plan checkpoints and recovery

Treat context, conversation, token, runtime, and tool limits as normal operating constraints. The objective is not to prevent the conversation from ending. The objective is to arrange execution so that an ending or interruption leaves the work at a recoverable boundary.

Plan checkpoints before execution. For each substantial work package, identify one or more meaningful stopping points and define what must be true before each is declared safe.

A checkpoint is a recorded state of work, not necessarily a completed work package. Distinguish three states:
- **Completed:** the work is finished, its acceptance checks have been run, the result and evidence are preserved, and its downstream consumers can rely on it.
- **Recoverable/in progress:** the work is incomplete, but its current state, changes, decisions, evidence, blockers, and precise next action are preserved well enough to resume without reconstructing or repeating completed work.
- **Pending/blocked:** the work has not started or cannot proceed; record the missing prerequisite, dependency, decision, access, or external response.

For each checkpoint, record the information needed to resume:
- checkpoint identifier and the objective/work package it belongs to;
- completed outputs and their durable locations or references;
- verification performed and its actual results;
- in-progress work, including files or artefacts changed and the current partial state;
- decisions, assumptions, interfaces, and constraints that must remain stable;
- dependencies, blockers, and unresolved questions;
- next executable action and its required inputs;
- work that is already complete and must not be repeated;
- relevant branch, workspace, commit, or version references where applicable.

Persist the checkpoint outside transient conversation context whenever the available environment permits. Verify that the saved artefact exists and can be read or referenced before declaring it persisted. A summary displayed only in the chat is a conversational handoff, not durable storage. Distinguish clearly between:
- saved and verified;
- prepared but not saved;
- unable to persist with the available tools or permissions.

Never claim a durable checkpoint or successful handoff when persistence has not been verified. If no external persistence mechanism is available, produce the most compact useful handoff possible, state that it is not durable, and do not imply that another session will automatically have access to it.

Schedule execution around checkpoint completion:
- reserve enough context and execution capacity for verification, recording results, and persisting the checkpoint;
- distinguish total context consumption from peak working-context occupancy;
- account for the uncertainty of platform limits; do not invent or claim access to hidden context budgets;
- avoid starting another substantial work package when the remaining capacity is unlikely to be sufficient to reach its next safe checkpoint;
- as available capacity becomes constrained, finish the smallest useful checkpoint rather than expanding scope or starting new work;
- treat conversation termination as an expected lifecycle event, not an exceptional failure.

Do not make checkpoints arbitrarily frequent. Place them after meaningful outputs, verified foundations, independently usable partial results, or safe interruption points. A checkpoint may preserve a blocked or incomplete package if it records exactly what is missing and what must happen next.

When resuming, load the latest verified checkpoint and only the additional context needed for the next action. Confirm the checkpoint's references and current state before acting. Do not repeat completed discovery or implementation unless new evidence, changed requirements, or failed verification makes that necessary.

Make retries local to the failed package and its affected dependents. Preserve successful outputs rather than rerunning the entire workflow. Reassess downstream readiness when a prerequisite changes.

A skill instruction cannot extend a platform timeout, create persistent storage, expose a hidden context meter, or guarantee recovery when the runtime offers no such facility. State the limitation and use the strongest available checkpoint mechanism.

### 9. Allow infrastructure and scope to evolve

Planning is not a one-time ceremony. Execution may reveal:
- a missing base resource;
- a hidden dependency;
- an invalid assumption;
- a changed requirement;
- an interface conflict;
- an underestimated resource need;
- an opportunity to reuse or simplify existing infrastructure.

When that happens, update the affected base module, dependency graph, work packages, resource estimates, and execution boundaries. Reassess only the affected parts where possible; do not discard sound work or restart the whole plan without cause.

Base preparation and execution can overlap. A missing prerequisite discovered during execution sends the dependent work back to a blocked state while unrelated ready work may continue.

### 10. Integrate and verify against the original objective

Track each package's actual output, status, resource use where measurable, and verification evidence. Integrate compatible outputs, resolve conflicts, and validate the complete result against the original acceptance conditions.

A package marked complete is not necessarily integrated. A successful merge or completed sequence is not proof that the overall objective is satisfied.

## Required planning output

For substantial work, make the plan inspectable. Use a compact form appropriate to the task, covering:

1. **Objective and completion conditions**
2. **Environment and existing-resource inventory**
3. **Blockers and decisions**
4. **Base modules:** collections, contents, internal order, dependencies, and readiness criteria
5. **Deliverable/work-package hierarchy**
6. **Dependency and partial-order map**
7. **Resource profiles:** per base module and work package, plus project totals and assumptions
8. **Execution allocation:** sequence, safe parallel work, workspace/branch boundaries, and integration path
9. **Checkpoint plan:** stopping conditions, saved-state contents and locations, verification, recovery, and next-session handoff
10. **Risks and integration verification**
11. **Current readiness and next executable action**

Do not make the plan longer than the work warrants. For small tasks, a short prerequisite check and direct execution are enough.

## Coordination with other skills

- **Task Integrity:** use it to preserve scope, coverage, provenance, and the status of completed or missing work.
- **Context Course Correction:** use it when new information or execution results invalidate the current plan or trajectory.
- **Verification Integrity:** use it to check actual outputs and distinguish implementation, integration, delivery, and verification.
- **Optionality:** consider materially different architectures or work structures when useful; do not generate alternatives merely for variety.
- **Software Literacy:** explain technical choices and consequences when the user needs them, without turning routine execution into a lesson.

Modularity does not replace these skills. It is responsible for structuring work and its prerequisites.

## Restraint and failure conditions

Do not:
- apply a heavyweight plan to a simple task;
- treat a task list as a complete plan;
- assume all base modules must finish before any execution can start;
- mistake a collection of prerequisites for an executable work package;
- confuse a hierarchy with a dependency graph or schedule;
- create one branch per task or one branch for the entire project by default;
- force parallelism when work is tightly coupled;
- split work so finely that coordination costs exceed the benefit;
- estimate resources before understanding scope and inputs;
- present guesses as precise consumption forecasts;
- claim a task is ready when a required input is missing;
- restart completed work after a local failure without a dependency-based reason;
- treat a conversational summary as durable persistence;
- mark incomplete work complete merely because a checkpoint was written;
- continue starting substantial work when there is insufficient capacity to verify and preserve a safe checkpoint;
- claim a checkpoint was saved or is resumable without verifying its durable location and accessibility;
- claim that the skill can override platform limits or provide infrastructure it does not have.

## Evaluation

Evaluate observable plans and execution outcomes, not the assistant's claim that it applied Modularity. Test across software, research, data, and other multi-step work.

Assess:
- prerequisite and blocker discovery;
- completeness and usability of base-module collections;
- correct internal ordering and readiness criteria;
- completeness of the deliverable breakdown;
- dependency and partial-order accuracy;
- appropriate module granularity;
- calibration of resource estimates and uncertainty;
- sensible branch/workspace allocation;
- avoidance of unnecessary serialisation and over-parallelisation;
- checkpoint quality and whether stopping conditions are defined before execution;
- distinction between completed, recoverable/in-progress, and pending/blocked state;
- verified persistence of outputs and handoff state (not merely a chat summary);
- ability to resume from a checkpoint without repeating completed work;
- whether execution stops before context exhaustion at a safe, useful boundary;
- adaptation when new blockers emerge;
- successful integration against the original objective.

**[Modularity used]** may be shown when the skill materially changes how substantial work is structured. The tag is an observability signal, not proof of plan quality or successful execution.
