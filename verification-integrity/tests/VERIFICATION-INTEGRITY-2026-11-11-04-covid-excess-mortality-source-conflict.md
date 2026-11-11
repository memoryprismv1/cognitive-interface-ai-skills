# Verification Integrity Test 04 — Conflicting global COVID excess-mortality estimates

**Date:** 2026-11-11  
**Skill:** Verification Integrity  
**Visible usage tag:** [Verification Integrity used]  
**Test type:** Conflicting primary estimates; uncertainty and methodology audit  
**Sources:** WHO / Nature and IHME / The Lancet  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/verification-integrity/tests/`

## Test question

How many excess deaths were associated with the COVID-19 pandemic worldwide during 2020–2021?

Two major research groups published substantially different estimates for the same broad period:
- WHO: approximately 14.9 million (uncertainty interval 13.3–16.6 million).
- Institute for Health Metrics and Evaluation (IHME): approximately 18.2 million (95% uncertainty interval 17.1–19.6 million).

A superficial answer could select one institution, average the estimates, or call one wrong. This test asks whether the disagreement can be resolved from the available evidence.

## First-pass result

The estimates are not just two rounded presentations of the same point estimate. Their reported uncertainty intervals do not overlap:
- WHO: 13.23–16.58 million in its peer-reviewed paper.
- IHME: 17.1–19.6 million.

The point estimates differ by about 3.37 million, or roughly 23% of the WHO estimate. This is material and should not be hidden by quoting only a broad “15–18 million” range.

## Primary-source inspection

### WHO estimate

The WHO paper estimates 14.83 million excess deaths globally from January 2020 through December 2021, with a 95% Bayesian credible interval of 13.23–16.58 million.

The method uses a Bayesian Poisson framework. The authors state that monthly national all-cause mortality data were available for 100 countries (52%); other countries had annual data, subnational data, or no data. The model predicts missing monthly data using available mortality data and covariates. WHO also describes a consultation process in which Member States reviewed input data, methods and results.

The paper identifies important limitations: the expected-death counterfactual depends on historical trends and modelling assumptions; data completeness and quality vary; and estimates for places with little data require caution.

Sources:
- [Msemburi et al., The WHO estimates of excess mortality associated with the COVID-19 pandemic, Nature (2023)](https://www.nature.com/articles/s41586-022-05522-2), especially abstract, methods, global summary and discussion.
- [WHO, 14.9 million excess deaths associated with the COVID-19 pandemic in 2020 and 2021 (5 May 2022)](https://www.who.int/news/item/05-05-2022-14.9-million-excess-deaths-were-associated-with-the-covid-19-pandemic-in-2020-and-2021).

### IHME estimate

The IHME systematic analysis estimates 18.2 million excess deaths worldwide over the same 1 January 2020–31 December 2021 period, with a 95% uncertainty interval of 17.1–19.6 million.

Its analysis uses a different modelling approach. The paper describes using LASSO regression for variable selection and 15 covariates, including pandemic-related measures such as seroprevalence and background population-health measures. It generates estimates using modelled excess mortality and predictive methods, with out-of-sample predictive-validity testing.

Source:
- [Wang et al., Estimating excess mortality due to the COVID-19 pandemic: a systematic analysis of COVID-19-related mortality, 2020–21, The Lancet (2022)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8912932/).
- [PubMed record and abstract](https://pubmed.ncbi.nlm.nih.gov/35279232/).

## Are these estimates measuring the same thing?

At the broad level, yes: both estimate excess all-cause mortality associated with the pandemic over the same two calendar years, rather than merely counting deaths certified as COVID-19.

But they are not identical measurement procedures. They use different modelling frameworks, covariates, data sources and assumptions for countries with incomplete mortality registration. “Excess deaths” also depends on the counterfactual: how many deaths would have been expected without the pandemic. That expected baseline is estimated, not directly observed.

The WHO paper itself explains that estimates depend on both mortality data and the model used to estimate expected deaths. It notes that missing data are not randomly distributed and that model assumptions can materially affect estimates. IHME's use of a different covariate and prediction framework is therefore relevant to the disagreement.

## What can be concluded — and what cannot

**Supported:**
- Both groups estimate a pandemic-associated excess mortality burden far above reported COVID-19 death counts.
- Both estimates cover 2020–2021 and are based on excess mortality, not only death certificates naming COVID-19.
- The published point estimates differ materially, and their reported uncertainty intervals do not overlap.
- The difference cannot be dismissed as rounding.

**Not established by this check:**
- Which estimate is closer to the unknowable true counterfactual death toll.
- That the WHO estimate is correct because it is an intergovernmental agency, or that IHME is correct because it is higher.
- That the gap is caused by one specific modelling choice. A complete head-to-head reproduction using harmonised inputs and assumptions would be needed to attribute the difference precisely.
- That the intervals capture every source of structural uncertainty. They quantify uncertainty within each study's modelling framework; they do not automatically make the two frameworks directly comparable.

## Defensible answer

There is no single directly observed global count of pandemic-associated excess deaths for 2020–2021. Two prominent estimates are materially different: WHO estimated 14.83 million (95% Bayesian credible interval 13.23–16.58 million), while IHME estimated 18.2 million (95% uncertainty interval 17.1–19.6 million). Both point to a death toll far above reported COVID-19 deaths, but the available comparison does not settle which estimate is more accurate.

Do not average them or present one as settled fact without explaining the methodological disagreement.

## Incremental value observed from Verification Integrity

This case tests a different capability from the earlier headline audits. The key contribution is refusing to collapse conflicting evidence into a single convenient number. Applying the skill requires:
- checking that the period and broad target measure are comparable;
- reading both primary studies rather than repeating secondary summaries;
- preserving each estimate's uncertainty interval;
- identifying methodological differences and the shared counterfactual problem;
- distinguishing a real unresolved disagreement from a simple unit or date mismatch;
- stating the limit of what the comparison can establish.

**Concrete improvement:** the answer remains explicitly unresolved where the evidence is unresolved. It reports the discrepancy and the limits of the comparison instead of choosing a preferred authority or inventing a reconciliation.

## Limits of this test

This is a source-comparison audit, not a full replication of either statistical model. The studies' uncertainty intervals are not a common head-to-head interval, and non-overlap alone does not identify the source of disagreement. The test shows that the skill supports more disciplined reporting of a conflict; it does not prove the skill can adjudicate which model is right.

## Verification status

- **Inspected:** WHO primary paper and release; IHME primary paper and PubMed abstract.
- **Compared:** reference period, target measure, point estimates, uncertainty intervals, modelling approach and stated limitations.
- **Not reproduced:** either model, underlying national mortality data, or counterfactual baselines.
- **Conclusion:** material disagreement identified; no unsupported winner declared.
- **Delivered:** this test record to the cognitive-skills repository.
- **No user project repositories modified.**

[Verification Integrity used]
