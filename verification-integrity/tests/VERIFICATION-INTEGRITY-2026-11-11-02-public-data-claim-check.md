# Verification Integrity Test 02 — Public-data claim and derived summary

**Date:** 2026-11-11  
**Skill:** Verification Integrity  
**Visible usage tag:** [Verification Integrity used]  
**Test type:** Independent claim check and small derived evidence artifact  
**Source domain:** OECD public report and OECD Data Explorer  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/verification-integrity/tests/`

## Why this test

Test the skill on material unrelated to the user's projects. The target is a factual claim in a public OECD report, not a project repository or an example curated by the user.

Question: **Did only 9% of global plastic waste get recycled in 2019, and what does that percentage actually measure?**

## First-pass answer before applying the skill

A quick reading of the OECD headline yields: "Only 9% of global plastic waste was recycled in 2019."

That statement is directionally correct but too compressed to distinguish collection from successful recycling. A reader could easily confuse the 15% collected for recycling with the 9% ultimately recycled.

## Verification actions prompted by the skill

1. Inspect the primary report passage rather than relying on a search-result summary.
2. Separate collection from recycling output and account for recycling residues.
3. Check the arithmetic against the reported total.
4. Check the dataset description to establish the nature and scope of the underlying figures.
5. State what this check does and does not establish.

## Evidence inspected

### OECD report

The OECD *Global Plastics Outlook* states that global plastic waste in 2019 was 353 million tonnes (Mt). Of this, 55 Mt was collected for recycling; 22 Mt became recycling residue requiring further disposal; and 33 Mt, or 9% of total plastic waste, was ultimately recycled. The report's Figure 1.1 explicitly labels the 33 Mt as 9% of 353 Mt.

Source: [OECD, Global Plastics Outlook — Overview and policy highlights, section 1.3.1 and Figure 1.1](https://www.oecd.org/en/publications/global-plastics-outlook_de747aef-en/full-report/component-6.html).

### OECD dataset description

The OECD Data Explorer describes its 2019 plastic-waste dataset as estimates for 15 global regions of the OECD ENV-Linkages model. It says waste is calculated from plastics use using a methodology based on product lifespans, and points to the report annex for the complete methodology.

Source: [OECD Data Explorer — Plastic Waste in 2019](https://data-explorer.oecd.org/vis?df%5Bag%5D=OECD.ENV.EEI&df%5Bds%5D=dsDisseminateFinalDMZ&df%5Bid%5D=DSD_PW_2019%40DF_PW_2019).

## Derived check

- Total plastic waste: 353 Mt
- Collected for recycling: 55 Mt
- Recycling residue requiring further disposal: 22 Mt
- Net recycled: 55 - 22 = 33 Mt
- Net recycled share: 33 / 353 × 100 = 9.35%, reported by OECD as 9%

The arithmetic is consistent with the report. The 55 Mt collection figure is not the amount successfully recycled.

## Result

**The claim is supported, with an important qualification.** OECD estimates that 33 Mt of 353 Mt of global plastic waste was ultimately recycled in 2019 (about 9%). 55 Mt was collected for recycling, but 22 Mt of that amount became residue and required further disposal.

The result is an estimate for the 2019 reference year, not a current-year measurement. The Data Explorer identifies the figures as model-based estimates across 15 regions; this check does not independently reproduce the OECD model or validate its assumptions.

## Incremental value observed from Verification Integrity

Compared with the compressed first-pass answer, applying the skill caused the verification to inspect the primary passage, distinguish the collection input from net recycled output, reconcile the figures arithmetically, and qualify the modelled nature and reference year of the data.

**Concrete improvement:** it prevents the 55 Mt collected-for-recycling figure from being misreported as 55 Mt successfully recycled, and makes the 9% claim traceable to the underlying quantities.

**Limit:** this is a small, favourable example. The check demonstrates a useful verification habit on one claim; it does not establish that the skill reliably improves performance across task types or that the OECD estimates themselves are correct.

## Verification status

- **Inspected:** OECD report passage and OECD Data Explorer dataset description.
- **Calculated:** net recycled quantity and share.
- **Cross-checked:** derived arithmetic against the report's stated 33 Mt / 9%.
- **Not independently verified:** OECD model inputs, assumptions, or regional source data.
- **Delivered:** this test record to the cognitive-skills repository.
- **No user project repositories modified.**

[Verification Integrity used]
