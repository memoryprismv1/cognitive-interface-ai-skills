# Verification Integrity Test 01 — Verify the CCTV reconstruction deliverables at their destination

**Date:** 2026-11-11  
**Skill:** Verification Integrity  
**Visible usage tag:** [Verification Integrity used]  
**Test type:** Destination and artifact verification  
**Target:** `memoryprismv1/faking-vision`, current `main` tree  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/verification-integrity/tests/`

## Requested outcome used for the test

The Faking Vision CCTV reconstruction task is documented as requiring three packet outputs with populated snapshot evidence, a reconstructed video, and merged object/temporal data.

The test question is whether the actual files at the intended GitHub destination satisfy those deliverables—or whether a convincing README/process record could obscure missing outputs.

## Destination inspected

GitHub repository: `memoryprismv1/faking-vision`  
Target directory: `PACKETS/examples/videos/CCTV_Snapshot_TD_Reconstruction_Experiment/`  
Branch: `main`  
Tree inspected: `6d47e1f6636c85fe13134a10c575ebe8b4de868f`

This is a check of the current repository state. It does not establish when each artifact was added or whether this exact tree was the state at the time of the original handoff.

## Artifact verification

| Requested output | Current destination status | What was checked |
|---|---|---|
| Three packet directories | **Delivered** | PKT-CCTV-001, 002 and 003 all exist |
| Populated snapshot evidence | **Delivered; references checked** | Manifest counts and corresponding image paths exist |
| Reconstructed video | **Delivered; not playback-tested** | MP4 exists at target path; Git tree reports 11,465,118 bytes |
| Merged object inventory | **Not present in this experiment directory** | No merged/global OI artefact at the target directory root |
| Merged temporal data | **Not present in this experiment directory** | No merged/global TD artefact at the target directory root |
| Canonical FV compile | **Not delivered / explicitly not claimed** | README says this is not a canonical compile; process log says FV CLI was not run |

### Snapshot counts

- **PKT-CCTV-001:** 52 verification images and 10 object crops.
- **PKT-CCTV-002:** 106 full-frame verification images and 8 object crops.
- **PKT-CCTV-003:** 105 full-frame verification images and 8 object crops.

The manifests were inspected and their referenced image paths were checked against the repository tree, respecting each manifest's path convention. No missing snapshot/crop references were found.

## Verification findings

### 1. The reconstruction video is actually present

The MP4 is present in the intended directory in the current Git tree, at 11,465,118 bytes. This establishes repository delivery and non-zero file size, not that the video decodes, plays correctly, or faithfully represents all three packets. Playback and content review were not performed.

### 2. Snapshot folders are populated, not merely described

All three packet folders contain snapshot evidence. The manifests enumerate 52, 106 and 105 verification frames respectively, plus 10, 8 and 8 object crops. Their references resolve to files in the repository tree.

This is stronger than relying on the packet README's statement that snapshots exist: the actual destination paths were checked.

### 3. The merged outputs are absent from this experiment directory

The target directory contains the MP4, three packet folders, README, process log and provenance note. It contains no merged/global OI or TD output.

There is a separate `PACKETS/examples/cctv/CCTV_Storage_Crisis/MERGED_Global/` directory elsewhere in the repository. It is a different named example; its presence is not evidence that this CCTV Snapshot TD Reconstruction experiment has merged outputs. The two must not be conflated.

### 4. A packet-level source-file statement is contradicted by the destination

`PKT-CCTV-001/README.txt` says `part_01.webm` is included at the packet root. No such source file exists in that packet directory in the current Git tree.

The experiment-level `README.md` and `SOURCE_AND_PROVENANCE.md` say the three source segments are not stored in the repository because of GitHub file-size restrictions. Those broader statements match the tree. The packet-level statement is stale or incorrect and should not be relied on.

### 5. Packet completeness is not uniform

- PKT-CCTV-001 has OI/MSRM/TD/PC/TIR, a validation report and a dispute record.
- PKT-CCTV-002 has OI/MSRM/TD and snapshot evidence, but no PC, TIR, validation report or dispute file in its current directory. Its README labels it an initial analysis packet, not merged, validated or compiled.
- PKT-CCTV-003 has OI/MSRM/TD/PC/TIR, a validation report and a dispute record; its README records open issues and says it is not merged or compiled.

The existence of three directories therefore does not mean three packets have reached the same completion stage.

## Result

**Partially delivered at the current destination.**

The current repository contains all three packet directories, populated snapshot evidence and a non-empty reconstruction MP4. It does not contain merged object and temporal outputs in this experiment directory, and it does not claim a canonical FV compile. One packet README also makes a false source-file inclusion claim.

The current README/process log are relatively explicit about the experimental boundary. The remaining problem is not absence of all artifacts; it is that the requested deliverable set is not complete as a merged/compiled result, and one packet-level description contradicts the actual repository.

## What was and was not verified

- **Inspected:** current Git tree, target directory contents, packet README files, experiment README, process log, provenance note, snapshot manifests and PKT-CCTV-001 validation report.
- **Checked:** packet directory existence, image counts, manifest path resolution, MP4 path and reported size, presence/absence of merged files in the target directory.
- **Not tested:** MP4 decoding/playback, visual fidelity of the reconstruction, complete packet semantic validity, exhaustive source-frame coverage, FV CLI compile, or cross-packet identity correctness.
- **Not changed:** no Faking Vision files were modified.
- **Delivered:** this test record only, to the cognitive skills repository.

## Skill assessment

The useful behaviour was to inspect the requested outputs at the destination, rather than infer completion from process documentation. The result is neither “missing” nor “done”: several substantial artifacts are present, but the merged deliverables are absent from this experiment directory and the reconstruction itself was not playback-tested. The test also caught a concrete documentation contradiction.

[Verification Integrity used]
