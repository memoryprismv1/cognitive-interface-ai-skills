# Modularity Test 02 — Ordered prerequisite collections

**Date:** 2026-11-13  
**Skill:** Modularity  
**Status:** Test specification; not yet executed  
**Task type:** Research and analysis

## Scenario

A user requests a comparative research report across several technical approaches. The final analysis requires:
- a source collection;
- access to full-text material where possible;
- a classification scheme;
- a comparison matrix;
- a written synthesis;
- references and evidence checks.

Not all source material is immediately available. Some sources may be inaccessible or only available as abstracts. The classification scheme may need revision after initial reading.

## Test objective

Determine whether the agent recognises base modules as collections that require their own ordering, and whether it permits ready work to proceed without imposing a single global preparation gate.

## Expected behaviour

1. Identify source discovery, retrieval, access checking, provenance capture, and coverage assessment as distinct preparation activities.
2. Group them into a coherent source-collection base module.
3. Record the internal order: discover → retrieve → check access/provenance → classify coverage → assess readiness.
4. Identify other foundations, such as scope criteria and the comparison dimensions, and map their dependencies.
5. Distinguish a hard blocker (a missing source required for a specific comparison) from a limitation that can be disclosed while other work proceeds.
6. Permit analysis of already-ready source groups while unresolved retrieval continues elsewhere.
7. Estimate preparation consumption separately from reading, analysis, synthesis, and validation.
8. Record confidence and unknowns in estimates; avoid false precision.
9. Update the collection and downstream plan when a source is unavailable or reveals a new comparison requirement.
10. Preserve the distinction between directly inspected full text, abstracts, secondary summaries, and inference.

## Failure indicators

- Calls the source list complete merely because search results were returned.
- Treats source discovery and source analysis as the same work package.
- Fails to record provenance or access limitations.
- Blocks the entire report while unrelated ready source groups could be analysed.
- Continues downstream work that specifically requires a missing source.
- Fails to update the plan when the source collection changes.
- Treats estimates as exact measurements.

## Evaluation record

To be completed after a skill-enabled run and a comparable baseline run.

| Measure | Result |
|---|---|
| Base collection definition | Not evaluated |
| Internal ordering | Not evaluated |
| Readiness criteria | Not evaluated |
| Local vs global blockers | Not evaluated |
| Preparation/execution estimate distinction | Not evaluated |
| Evidence provenance | Not evaluated |
| Adaptation to missing sources | Not evaluated |

## Evidence boundary

This is a designed test case, not an executed research study. It checks planning behaviour and evidence discipline, not the truth of the research conclusions produced in a later run.
