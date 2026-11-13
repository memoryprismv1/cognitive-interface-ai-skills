# Modularity

**Skill:** `modularity`

**Status:** Initial research-informed design; operational effectiveness not yet validated.

**Core rule: Establish what the work needs before dividing up the work that will use it.**

## Purpose

Modularity helps an AI agent organise substantial work into executable structures without treating a large objective as one continuous workflow or splitting it into arbitrary tiny tasks.

The capability starts before execution planning. It identifies blockers and prerequisites, builds base modules as coherent collections, establishes their internal ordering and readiness conditions, and then decomposes the intended deliverables into work packages. It maps dependencies, estimates consumption, chooses useful execution boundaries, and adapts when work reveals missing foundations.

The practical motivation is straightforward: an agent should organise the work before attempting it. A plan that lists implementation activities but omits the environment, resources, information, interfaces, access, or other prerequisites is not ready to execute.

## 1. Problem being addressed

Long or multi-part AI tasks often collapse several different planning problems into one list:
- discovering what resources and conditions are available;
- preparing foundations needed by later work;
- defining the actual deliverables;
- ordering dependent activities;
- estimating resource use;
- deciding what should be isolated, grouped, parallelised, or integrated;
- tracking completion and recovering from interruptions.

When those are not distinguished, an agent may begin visible implementation before its prerequisites exist, put unrelated work into one branch or execution context, create excessive branches for tightly coupled work, underestimate resource consumption, or repeat completed work after a local failure.

The problem is not solved by adding more tasks to the list. It requires a representation of foundations, deliverables, dependencies, resources, and execution boundaries.

## 2. What Modularity is—and is not

Modularity is a general-purpose planning and coordination capability. Its responsibility is to structure work before and during execution.

It is not:
- a generic instruction to break everything into smaller tasks;
- a rule that every task needs its own branch or agent;
- a fixed top-down sequence in which all preparation must finish before anything can start;
- a project-management template imposed on every simple request;
- a guarantee that a model can predict exact token consumption or execution time;
- a runtime engine that can extend platform limits or preserve state without supporting infrastructure.

It distinguishes four key objects:

1. **Base modules:** collections of prerequisites that enable later work. They may contain resources, information, tools, configuration, access, specifications, interfaces, and internal ordered preparation activities.
2. **Work packages:** bounded, deliverable-oriented units of work.
3. **Dependencies:** required relationships and partial ordering between base modules, activities, and work packages.
4. **Execution boundaries:** the chosen branches, workspaces, agents, batches, or sessions used to carry out coherent packages.

A base module is not the same thing as an execution module. A base module can be a collection that must be assembled and validated before a dependent package is ready. Its constituent work may itself have ordering and resource requirements.

## 3. Research foundation

No single research tradition establishes the complete skill. The design draws on several bodies of work, and the evidence for each must remain within its actual scope.

### A. Construction play and open-ended materials: foundations emerge through interaction with resources

Cankaya, O., Rohatyn-Martin, N., Buro, K., Bulut, O., Taylor, K., et al. (2025). **Loose parts play encourages spontaneous science, technology, engineering, and mathematics (STEM) behaviours.** *Communications Psychology*, 3, 183.  
[https://doi.org/10.1038/s44271-025-00362-y](https://doi.org/10.1038/s44271-025-00362-y)

This within-subjects study observed 60 young children (mean age approximately 58.6 months) during unstructured solitary play with loose parts and with limited-function toys. Children demonstrated significantly more STEM behaviours with loose parts, including constructing structures, explaining how things work, communicating goals, and exploring mathematical ideas.

Loose parts are materials children can repurpose. The paper describes children observing properties such as weight, texture, flexibility, and balance, and choosing materials according to perceived possibilities for action.

**What this supports:** open-ended resources can shape exploration, construction, and the behaviours that emerge. Available materials are not incidental to the activity; they affect what can be attempted.

**What it does not establish:** the study examined solitary play, not a group of children jointly managing a construction project. It does not show that children use formal base modules, dependency graphs, resource estimates, or project plans. The skill's infrastructure analogy is an engineering hypothesis inspired by the observed relationship between materials and activity.

Additional source: [PubMed record](https://pubmed.ncbi.nlm.nih.gov/41350933/).

### B. Hierarchical Task Network planning: goals, compound tasks, primitive actions, and ordering

Nau, D., Au, T.-C., Ilghami, O., Kuter, U., Murdock, J. W., Wu, D., & Yaman, F. (2003). **SHOP2: An HTN Planning System.** *Journal of Artificial Intelligence Research*, 20, 379–404.  
[Paper](https://www.cs.umd.edu/~nau/papers/nau2003shop2.pdf)

Hierarchical Task Network (HTN) planning represents plans through the decomposition of higher-level tasks into smaller subtasks. SHOP2 supports methods that decompose tasks into partially ordered subtasks and can interleave subtasks from different tasks.

**What this supports:** a goal, a compound task, and an executable action are different levels. Their relationships and ordering need to be represented explicitly. Partial ordering is more expressive than forcing every subtask into one total sequence.

**Design implication:** Modularity separates the objective, base-module collections, deliverable hierarchy, dependency graph, and executable work packages. It allows independent preparation or execution to overlap where dependencies permit.

### C. Work Breakdown Structures: completeness of deliverables is not the schedule

Project Management Institute. **Practice Standard for Work Breakdown Structures — Second Edition.**  
[PMI reference](https://www.pmi.org/learning/library/practice-standard-work-breakdown-structures-8063)

PMI defines a work breakdown structure as a deliverable-oriented hierarchical decomposition that organises the total scope of work. It distinguishes the WBS—which defines what is in scope—from the activity definitions and schedule that describe how and when work is performed. Its 100% rule requires child elements to account for the complete scope represented by their parent.

**What this supports:** a plan should be checked for scope completeness, not merely whether its activities sound plausible. A deliverable hierarchy and an execution schedule answer different questions.

**Design implication:** use a deliverable-oriented breakdown alongside a separate dependency and resource plan. Do not mistake a numbered checklist for a complete execution architecture.

### D. Resource-constrained project scheduling: precedence and scarce resources must be planned together

Hartmann, S., & Briskorn, D. (2022). **An updated survey of variants and extensions of the resource-constrained project scheduling problem.** *European Journal of Operational Research*, 297(1), 1–14.  
[https://doi.org/10.1016/j.ejor.2021.05.004](https://doi.org/10.1016/j.ejor.2021.05.004)

Gómez Sánchez, M., Lalla-Ruiz, E., Fernández Gil, A., Castro, C., & Voß, S. (2023). **Resource-constrained multi-project scheduling problem: A survey.** *European Journal of Operational Research*, 309(3), 958–976.  
[https://doi.org/10.1016/j.ejor.2022.09.033](https://doi.org/10.1016/j.ejor.2022.09.033)

This research area studies schedules subject to precedence relationships and limited resources. Multi-project variants also consider work competing for shared resources.

**What this supports:** identifying dependencies is not enough. A feasible schedule must also account for resource availability. Parallel work can compete for the same limited resources, and the shortest dependency path does not necessarily produce the shortest feasible schedule.

**Design implication:** estimate resource consumption per base module and work package, then assess aggregate demand, concurrency, external waits, and bottlenecks. Distinguish estimated package effort from project elapsed time and critical-path duration.

### E. Distributed cognition: work is organised across people, artefacts, and environments

Hutchins, E. (1995). **Cognition in the Wild.** MIT Press.  
[Author's publications](https://pages.ucsd.edu/~ehutchins/vitae/pubs.htm)

Hollan, J. D., Hutchins, E., & Kirsh, D. (2000). **Distributed Cognition: A New Foundation for Human-Computer Interaction Research.** *ACM Transactions on Computer-Human Interaction*, 7(2), 174–196.

Distributed cognition studies cognitive processes as distributed across people and the artefacts and structures they use, rather than located only inside an individual mind.

**What this supports:** durable external representations and shared artefacts can participate in coordinated work. A plan, inventory, interface specification, repository, or progress record can be part of the working system rather than merely a transcript of it.

**Design implication:** preserve module boundaries, dependencies, resource inventories, and progress in inspectable artefacts when the task outlives one working context. This is a design inference, not evidence that a particular AI file format is optimal.

### F. Asynchronous software engineering agents: isolation and integration are architectural concerns

Geng, J., & Neubig, G. (2026). **Effective Strategies for Asynchronous Software Engineering Agents.** *Conference on Language Modeling (COLM 2026)*.  
[Conference paper](https://proceedings.colm.cc/paper_files/paper/2026/hash/3b5c10bf5d70533e955cba9fba491bf4-Abstract-Conference.html) · [arXiv version](https://arxiv.org/abs/2603.21489)

The authors identify problems in long-horizon software work: concurrent edits can interfere, dependencies are difficult to synchronise, and partial work is difficult to integrate. Their Centralized Asynchronous Isolated Delegation (CAID) approach uses a central manager, dependency-aware plans, isolated workspaces, asynchronous execution, and structured integration with executable verification.

The conference abstract reports absolute improvements over single-agent baselines of 25.6 percentage points on PaperBench and 14.7 percentage points on Commit0 in the reported evaluations.

**What this supports:** software-agent coordination benefits from explicit dependencies, isolated workspaces, central coordination, and a deliberate integration mechanism. It also shows why simply launching more agents or branches is not enough.

**Design implication:** choose branch/workspace boundaries around coherent, sufficiently independent work packages. Do not equate one task with one branch.

### G. Long-horizon agent context: execution state must survive changing working context

**COMPASS: Enhancing Agent Long-Horizon Reasoning with Evolving Context.** *ACL 2026*.  
[PubMed Central full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC13682274/)

COMPASS separates tactical execution, strategic oversight, and context organisation. It identifies long histories and irrelevant context as factors that can interfere with long-horizon reasoning and replanning.

**What this supports:** execution, oversight, and context organisation are different responsibilities. Long-running work needs a concise and relevant representation of progress.

**Design implication:** keep the overall objective, dependencies, completed outputs, blockers, and resume point available without carrying every intermediate execution detail into every subsequent step.

## 4. Design principles derived from the research

1. **Foundations before task scheduling.** Identify blockers and enabling resources before estimating the visible execution work.
2. **Collections before fragments.** Group related prerequisites into base modules with meaningful readiness criteria.
3. **Ordering is explicit.** Base modules can have internal dependencies; work packages can have dependencies across the hierarchy.
4. **Readiness is local.** Do not wait for every foundation in the project if a particular work package already has everything it needs.
5. **Hierarchy is not a schedule.** Deliverable structure, dependencies, and timing are separate representations.
6. **Resource demand constrains concurrency.** Parallelism is useful only when dependencies, isolation, and resource availability permit it.
7. **Branch boundaries follow coupling.** Group related changes; isolate genuinely independent deliverables.
8. **Plans remain revisable.** Execution can reveal missing resources, hidden dependencies, or changed requirements.
9. **State is externalised where possible.** Persist completed work, decisions, and recovery points instead of relying on conversational history alone.
10. **Planning must earn its cost.** Use as much structure as the task needs, but no more.

## 5. Proposed operating architecture

The skill uses five linked planning views:

1. **Objective and environment:** what is wanted, what exists, and what constraints apply.
2. **Base-module map:** prerequisite collections, their contents, internal order, dependencies, and readiness.
3. **Deliverable breakdown:** the work packages needed to achieve the objective, with scope and outputs.
4. **Dependency and resource plan:** partial ordering, blockers, per-module consumption, aggregate demand, and uncertainty.
5. **Execution and integration plan:** sequence, parallel opportunities, branch/workspace boundaries, checkpoints, recovery, and verification.

These are complementary views of one plan, not five mandatory documents. A lightweight task may need only a few lines.

## 6. Evaluation plan

The skill should be evaluated on tasks where a monolithic checklist or indiscriminate branch split is likely to fail. Compare skill-enabled and baseline plans under comparable conditions. Do not count a longer plan as a better plan.

### Core measures

- **Prerequisite recall:** relevant blockers and required foundations identified before execution.
- **Base-module quality:** collections are coherent, complete enough for their downstream use, and have clear readiness conditions.
- **Ordering correctness:** required prerequisite relations are represented; independent activities are not serialised without reason.
- **Scope coverage:** deliverable packages account for the objective without unrequested work.
- **Granularity:** packages are independently understandable and verifiable without excessive fragmentation.
- **Resource calibration:** estimates include appropriate dimensions, ranges, assumptions, and uncertainty.
- **Branch/workspace quality:** boundaries reflect coupling, file overlap, interfaces, and integration cost.
- **Feasibility:** plan accounts for available budgets and resource contention.
- **Adaptation:** a newly discovered blocker changes affected readiness and dependencies without destroying valid work.
- **Recovery:** interruption or local failure does not cause unnecessary repetition.
- **Outcome:** integrated result meets the original completion conditions.

### Evidence boundary

The research above motivates parts of the architecture. It does not establish that this exact skill improves AI planning, reduces token use, prevents timeouts, or produces better Git branching. Those are hypotheses to test.

The child-play analogy is deliberately limited. The loose-parts study supports the role of open-ended materials in children's observed exploration and construction behaviours. It does not establish that children use formal project-management methods, or that their behaviour directly validates this AI procedure.

## 7. Open research questions

The first version should be tested and revised around these unresolved questions:

- How large should a base module be, and how should the agent know when a collection is ready?
- How should the agent estimate resource consumption when model token accounting or execution limits are hidden?
- What level of file overlap or interface coupling should influence branch boundaries?
- When is a new branch more expensive than a shared branch?
- How much coordination overhead is introduced by additional agents or workspaces?
- How should estimates be recalibrated from actual resource use?
- How should the plan represent requirements that emerge only during execution?
- Which checkpoints best preserve progress without creating excessive bookkeeping?

## 8. Scope and implementation limits

Modularity can instruct an agent to inspect, plan, estimate, record state, choose work boundaries, and use available tools. Actual isolation, branch creation, parallel execution, durable checkpoints, token accounting, and timeout recovery depend on the host environment and permissions.

A skill file cannot extend a model's context window, increase an API quota, stop an external process that the interface cannot interrupt, or guarantee persistence across sessions. Where infrastructure is unavailable, the agent must state the limit and provide the strongest feasible handoff.

## References for follow-up

- Cankaya et al. (2025), [Loose parts play encourages spontaneous STEM behaviours](https://doi.org/10.1038/s44271-025-00362-y).
- Nau et al. (2003), [SHOP2: An HTN Planning System](https://www.cs.umd.edu/~nau/papers/nau2003shop2.pdf).
- Nau et al. (2001), [Total-Order Planning with Partially Ordered Subtasks](https://ijcai.org/proceedings/2001/59).
- Project Management Institute, [Practice Standard for Work Breakdown Structures](https://www.pmi.org/learning/library/practice-standard-work-breakdown-structures-8063).
- Hartmann & Briskorn (2022), [Updated survey of resource-constrained project scheduling](https://doi.org/10.1016/j.ejor.2021.05.004).
- Gómez Sánchez et al. (2023), [Resource-constrained multi-project scheduling survey](https://doi.org/10.1016/j.ejor.2022.09.033).
- Hutchins (1995), [Cognition in the Wild](https://pages.ucsd.edu/~ehutchins/vitae/pubs.htm).
- Hollan, Hutchins & Kirsh (2000), Distributed Cognition: A New Foundation for HCI Research.
- Geng & Neubig (2026), [Effective Strategies for Asynchronous Software Engineering Agents](https://proceedings.colm.cc/paper_files/paper/2026/hash/3b5c10bf5d70533e955cba9fba491bf4-Abstract-Conference.html).
- [COMPASS: Enhancing Agent Long-Horizon Reasoning with Evolving Context](https://pmc.ncbi.nlm.nih.gov/articles/PMC13682274/).
