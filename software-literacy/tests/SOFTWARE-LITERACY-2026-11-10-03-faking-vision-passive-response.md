# Software Literacy Test 03 — Faking Vision passive-response classification

**Date:** 2026-11-10  
**Skill:** Software Literacy  
**Visible usage tag:** [Software Literacy used]  
**Target project:** `memoryprismv1/faking-vision` (read-only inspection)  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/software-literacy/tests/`

## Test question

Can I identify a real logic flaw in an existing project, explain the effect in ordinary language, distinguish a demonstrated defect from a broader suspicion, and recommend a proportionate correction without rewriting the application?

## Result

**A concrete specification/implementation mismatch was found.**

The current `PACKETS/tools/FV_Edit_Visual_Workbench.html` defines:

```js
const passiveAffected = (env,oi) => {
  ...
  return [...new Set(oi.filter(o=>!o.is_living).filter(...).map(o=>o.id))];
};
```

The first filter excludes every object marked `is_living` before checking whether the environmental conditions match it.

The current authoritative `SPECIFICATION/FV_Working_Process_Specification.md` (environmental response section, lines 1950–1974) defines response classification by the change represented in the current edit:

- **Passive:** appearance or state changes, with no behaviour or spatial change asserted.
- **Active:** behaviour and/or location changes.

The specification also explicitly cautions against assuming that living objects must move under high stress. It does not say that living objects are incapable of passive responses.

### Reproduction

I evaluated the helper logic in isolation with a small input:

- Environment: light rain.
- Object A: a living palm tree, with its behaviour remaining still and its leaves represented as dry.
- Object B: a non-living roof.

The helper returned:

```json
{
  "livingPlant": [],
  "nonlivingRoof": ["roof_01"]
}
```

The tree is excluded solely because `is_living` is true; the roof is retained because it is not. The helper therefore cannot identify a living object as a passive-impact candidate, even where its type and description match the environmental rule.

This demonstrates the filter's behaviour. It does **not** establish that every living tree must be marked as affected by every rain event. Actual impact still needs to be supported by the source, task, or explicit test expectation.

## Why it matters

A living object's appearance or state can change without it changing behaviour or location. Examples include wet leaves, wet fur, or a change in surface appearance. Those are passive changes under the current FV definition.

The current filter creates a blind spot: the workbench can omit such an object from its passive-impact candidates. That can leave the packet's representation incomplete and can make later review or audit miss a relevant state change.

## Existing test coverage

The repository contains browser tests and a helper-level smoke test. The current smoke test checks that passive IDs resolve to OI objects and checks a negative sunlight case. The browser tests check reference validity, environmental edits, retained active responses, and history preservation.

The inspected tests do not assert that a living object can be represented as passively affected. The present checks can therefore pass while this exclusion remains.

Relevant files:

- `PACKETS/tools/FV_Edit_Visual_Workbench.html`
- `SPECIFICATION/FV_Working_Process_Specification.md`
- `PACKETS/tools/fv-editor-smoke-test.mjs`
- `tests/browser/environment-workbench.spec.js`

## Proportionate correction

Do not replace the filter with an unconditional rule that all living objects are passive. That would merely reverse the error.

Instead:

1. Separate **whether an object may be affected** from **whether its response is passive or active**.
2. Do not use `is_living` as a blanket exclusion from passive candidates.
3. Keep passive classification tied to the actual represented change: appearance/state only, with no behaviour or spatial change asserted.
4. Keep active classification tied to a supported behaviour and/or location change.
5. Add regression cases for a living plant with a passive appearance change, a living animal with a passive appearance change, and a living object with an active behaviour/location change. Include a non-living passive case as a control.
6. Ensure the OI record and edit-log record preserve the before/after state needed to audit the classification.

One further distinction is important: the current helper is a keyword-based candidate matcher, not evidence that an object actually changed. A future correction should preserve that distinction rather than silently turning a heuristic match into a verified observation.

## Verification boundary

- **Source inspection:** completed against the current `main` branch.
- **Specification comparison:** completed.
- **Reproduction:** the extracted helper logic was executed in isolation; the living plant was omitted and the non-living roof was included.
- **Existing test review:** completed.
- **Full browser suite / CI:** not run.
- **Faking Vision files changed:** none.
- **Cognitive skill test record:** this file only.

This is a demonstrated defect in the helper's eligibility filter and a test-coverage gap. It is not a claim that the entire environmental-response workflow is broken.

## Software Literacy assessment

The task required distinguishing a software rule from a domain rule, tracing the consequence of a small filter, reproducing the behaviour, checking it against the authoritative specification, and explaining the limits of the finding. The recommended fix is deliberately scoped to classification and regression coverage; no broad rewrite is justified.

[Software Literacy used]
