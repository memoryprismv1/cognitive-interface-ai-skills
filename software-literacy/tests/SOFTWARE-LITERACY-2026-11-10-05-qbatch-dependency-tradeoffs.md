# Software Literacy Test 05 — Explaining the downstream effects of a dependency

**Date:** 2026-11-10  
**Skill:** Software Literacy  
**Visible usage tag:** [Software Literacy used]  
**Target project:** `memoryprismv1/q-batch-of-evidence` (read-only inspection)  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/software-literacy/tests/`

## Test question

Can I explain the practical consequences of adding a new software dependency for a small feature, inspect the project's actual setup, and compare a simpler alternative without pretending the user asked for implementation?

## Scenario

A proposed feature: allow Q-Batch users to write configuration files in YAML and have the Python tools read them using PyYAML.

This is a hypothetical design exercise. No request to add YAML support was made, and no code was changed.

## Existing project facts inspected

- `requirements.txt` explicitly says there are no third-party Python dependencies; the prototype uses the Python standard library.
- The CI workflow runs Python 3.11, 3.12 and 3.13.
- The workflow currently compiles the project and runs its unit and experiment test suites without a dependency-install step.
- The repository's current implementation already uses JSON for manifests, contracts, schemas, run metadata and evidence artefacts.
- The CI workflow has an explicit read-only `contents: read` permission.

## What adding PyYAML would change

A **dependency** is another software component the project relies on. PyYAML would not be just one extra import in one file; it would become part of the environment needed to use and test the affected tools.

1. **Local setup:** users would need to install the package before running the YAML-enabled tools. The project would need clear installation instructions and a maintained dependency declaration.
2. **CI:** the workflow would need an installation step before tests. A clean runner currently succeeds without installing third-party Python packages.
3. **Version control and reproducibility:** the project would need a deliberate version policy. An unconstrained dependency can change behaviour when a fresh environment installs a newer release. Pinning or locking improves repeatability but adds maintenance.
4. **Security:** YAML parsing must be configured safely. Use `yaml.safe_load` for ordinary data rather than the general-purpose `yaml.load` loader, and test the accepted data shapes. A parser dependency also becomes part of the project's supply-chain surface.
5. **Compatibility and maintenance:** package availability and wheel/build behaviour must be checked across the supported Python versions and operating systems. Dependency updates become another thing to review.
6. **Offline or restricted environments:** a user who can currently run the standard-library tools without fetching packages may now need a preinstalled wheel or an approved package source.

The change is manageable, but it expands the project's setup and maintenance contract.

## Is there a simpler alternative?

There are two plausible alternatives:

- **Keep JSON:** it is already used throughout the repository, requires no additional dependency, and is suitable for machine-generated configuration. It is less pleasant for hand-edited comments and some authoring patterns.
- **Use TOML via Python's `tomllib`:** Python 3.11+ includes a standard-library TOML reader. The existing CI matrix starts at 3.11, so this avoids a third-party parser dependency if the project's supported runtime remains Python 3.11 or newer. TOML is designed for human-authored configuration, though it is not a drop-in replacement for YAML and has different syntax and capabilities.

YAML is justified if its authoring advantages are a real user requirement, especially if users already produce YAML elsewhere. If the goal is simply a readable configuration file, TOML is the lower-dependency option for the currently tested Python versions. If there is no concrete need for human-edited config, keeping JSON is the least disruptive choice.

## Recommendation

Do not add PyYAML merely because YAML is familiar. First establish that YAML compatibility is worth adding another runtime dependency.

If YAML is required:
- declare and constrain the dependency in one canonical dependency file;
- add a clean-environment CI install step;
- use safe parsing;
- test valid, malformed, unexpected-type and unsafe-tag inputs;
- test the full Python matrix;
- document the new setup requirement and how to install offline where necessary.

If the goal is human-readable configuration rather than YAML interoperability, prefer standard-library TOML on the existing Python 3.11+ support baseline.

## Verification boundary

- **Repository inspection:** completed against current `main`.
- **Dependency scenario:** analysed as a proposed change; not implemented.
- **Tests / CI:** not run; no code changed.
- **Claim scope:** this report explains likely consequences from the inspected repository structure. It does not claim PyYAML is incompatible, insecure by default in every use, or costly in this particular deployment.

## Software Literacy assessment

The exercise distinguishes a feature's visible code change from the wider dependency contract it creates. It explains the effects on installation, CI, reproducibility, security and maintenance, then offers a less disruptive alternative grounded in the project's actual Python matrix and existing JSON use.

[Software Literacy used]
