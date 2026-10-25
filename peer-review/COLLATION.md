# Peer Review Collation

## Purpose
Turn a mixed batch of supplied peer-review files into cumulative reports people can read. A batch may contain reviews of several unrelated subjects. The agent classifies the files and creates a separate report for each coherent topic.

Invoke when the user says **`peer-review collate`** or otherwise asks to collate a batch. Do not require the user to pre-sort it.

## Procedure

1. **Inventory every input.** Record filename/path, format, apparent subject, reviewer, date, target version, readability, and role where available. Never claim to have processed inaccessible or partially read files.
2. **Classify by the work actually reviewed.** Use content, target identifiers, versions, cited locations, and context; filenames are clues, not proof. Similar keywords alone do not justify merging. A file may contribute to multiple reports if it covers multiple subjects; preserve cross-references. Put material ambiguities in the exceptions list rather than guessing.
3. **Create one cumulative report per topic.** Each report should include:
   - topic, scope, and version boundaries;
   - plain-language executive summary;
   - convergent findings and unique observations;
   - disagreements and competing interpretations with their rationales;
   - unresolved questions;
   - status/revision history when evidence supports it;
   - coverage gaps, distinct from defects in the work;
   - proportionate next steps;
   - source files, reviewer/date/version and target locations where available.
4. **Synthesize, don't concatenate.** Deduplicate by underlying issue, not wording. Keep genuinely distinct issues separate. Write readable prose first; use tables only when useful. Do not substitute raw JSON for the human report.
5. **Preserve evidential status.** Distinguish reported claims, evidence actually inspected, independent corroboration, disputed/unresolved findings, and issues resolved or rejected by later evidence. Repetition is not independent corroboration unless independence is established. Preserve minority findings.
6. **Respect versions.** Do not silently merge materially different target versions into a current-state verdict. Label historical findings; disappearance from a later report alone does not prove resolution.
7. **Produce a batch index.** Map every input file to its topic report(s), or state its exception status and reason. Identify review reports, source/context files, structured exports, prior syntheses, duplicates, and unclassifiable files.
8. **Expose exceptions.** List unreadable/inaccessible files, ambiguous matches, cross-topic inputs, duplicates or likely duplicates, and context files not treated as reviews. Never silently drop an input.
9. **Deliver.** Default outputs are one human-readable cumulative report per topic, a batch index, and a concise exceptions/uncertainties section. Add structured findings or a machine-readable index when useful or requested, following [REPORT-FORMAT.md](REPORT-FORMAT.md). If separate files cannot be created, clearly label each report in one combined output.

## Default report outline

### Cumulative report — [Topic]
- Scope and source set
- Executive summary
- Convergent findings
- Unique findings
- Disagreements and alternatives
- Open questions and unresolved findings
- Status across versions
- Review coverage gaps
- Recommended next steps
- Sources and traceability

### Batch index
For every input: filename/path; assigned topic/report(s); role; reviewer/date/version if available; disposition; uncertainty or exclusion reason if applicable.

## Design principle
**The user supplies the batch; the agent discovers the structure.** Reduce the human's sorting and synthesis work rather than transferring it back to them.
