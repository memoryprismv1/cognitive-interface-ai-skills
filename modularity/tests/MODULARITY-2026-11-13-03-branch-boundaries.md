# Modularity Test 03 — Branch boundaries and over-fragmentation

**Date:** 2026-11-13  
**Skill:** Modularity  
**Status:** Test specification; not yet executed  
**Task type:** Software delivery and repository coordination

## Scenario

A code change involves:
- a shared data model;
- a backend implementation;
- a frontend component;
- automated tests;
- documentation.

The backend and frontend can be developed by separate workers only after a shared interface is agreed. Tests and documentation may touch files that overlap with implementation work. The repository uses a protected default branch and requires integration checks.

## Test objective

Determine whether the agent selects branch and workspace boundaries based on coupling and integration risk rather than mechanically using one branch for everything or one branch per task.

## Expected behaviour

1. Identify the shared data model and interface as foundational work.
2. Establish the interface before parallel implementation that depends on it, or explicitly plan a coordinated interface-change mechanism.
3. Group changes that are tightly coupled or likely to conflict.
4. Separate work packages only when outputs can be developed and reviewed independently.
5. Consider file overlap, shared state, API/schema changes, test ownership, integration cost, and rollback.
6. Provide a branch/workspace proposal with the reason for every boundary.
7. Avoid creating branches for non-code base collections or trivial tasks without a useful isolation benefit.
8. Reserve integration and verification work after dependent packages are ready.
9. Estimate coordination and integration cost, not only individual implementation cost.
10. Do not create or modify repository branches until execution is authorised and repository state/permissions have been checked.

## Failure indicators

- One branch for all unrelated work without considering isolation.
- One branch per task, including trivial or tightly coupled tasks.
- Parallelises frontend and backend before resolving their shared contract.
- Ignores file conflicts or shared interface changes.
- Omits an integration branch/path or integration tests.
- Reports a proposed branch plan as though branches have actually been created.

## Evaluation record

To be completed after a skill-enabled run and a comparable baseline run.

| Measure | Result |
|---|---|
| Coupling assessment | Not evaluated |
| Branch/workspace boundaries | Not evaluated |
| Interface readiness | Not evaluated |
| Coordination overhead | Not evaluated |
| Integration plan | Not evaluated |
| Execution authorisation and state checks | Not evaluated |

## Evidence boundary

This is a planning test specification. It does not establish a universal branch count or guarantee that the proposed isolation will eliminate merge conflicts.
