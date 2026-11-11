# Verification Integrity Test 03 — Audit of the “47% of jobs will be lost” claim

**Date:** 2026-11-11  
**Skill:** Verification Integrity  
**Visible usage tag:** [Verification Integrity used]  
**Test type:** Headline-to-source audit; competing estimates and scope reconciliation  
**Source domain:** Oxford University, UK Office for National Statistics, OECD-linked research  
**Test record location:** `memoryprismv1/cognitive-interface-ai-skills/verification-integrity/tests/`

## Test question

Does the well-known Frey and Osborne study establish that 47% of US jobs would be lost to automation?

This is deliberately harder than checking a single number. The public discussion contains a memorable percentage, headlines that sharpen its meaning, and other estimates that appear to contradict it.

## First-pass / headline-level interpretation

A casual reading of Oxford Martin School's 2013 news headline, **“Half of jobs to be lost to computerisation?”**, can leave the impression that the researchers forecast the loss of roughly half of US jobs within two decades.

That is not a faithful statement of the paper's measured result.

## Primary-source check

The peer-reviewed Frey and Osborne paper estimates the probability of computerisation for 702 detailed US occupations using a Gaussian process classifier. It places 47% of total US employment in its **high-risk category**, using a 0.7 probability threshold for occupation-level computerisation.

Crucially, the paper says its estimates concern the share of employment potentially substitutable by computer capital from a technological-capabilities perspective, over an **unspecified number of years**. It explicitly says it does not estimate how many jobs will actually be automated. It identifies adoption factors outside its model, including wages, capital prices, labour shortages, regulation and public acceptance.

Sources:
- [Frey & Osborne, The Future of Employment: How Susceptible Are Jobs to Computerisation? (2017 journal publication; PDF)](https://www.robots.ox.ac.uk/~mosb/public/pdf/2284/Frey%20and%20Osborne%20-%202017%20-%20The%20future%20of%20employment%20How%20susceptible%20are%20jobs.pdf), especially section 5.1 and section 6.
- [Oxford Martin School, “Half of jobs to be lost to computerisation?” (19 September 2013)](https://www.oxfordmartin.ox.ac.uk/news/201309futureofemployment).

## Competing estimates: do not flatten them into a single contradiction

The UK Office for National Statistics' review explains why later estimates differ:

- Frey and Osborne use an **occupation-based** approach. Their 47% is the share of US employment in occupations classified as high risk.
- Arntz, Gregory and Zierahn's OECD work uses a **task-based** approach, accounting for variation in tasks among people with the same occupation. ONS reports an estimate of 9% of jobs at high risk across 21 OECD countries.
- ONS says transferring the Frey–Osborne methodology to UK data produced 35%, while its own modified task-based approach is different.
- ONS also reports a PwC estimate of 38% for US jobs and 30% for UK jobs, and a McKinsey estimate below 5% of occupations at risk of full automation under a 100% threshold; using a 70% threshold yields around 30%.

Source: [UK Office for National Statistics, The probability of automation in England: 2011 and 2017 (25 March 2019), section 2](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/employmentandemployeetypes/articles/theprobabilityofautomationinengland/latest).

These figures are **not directly interchangeable**: they differ in geography, unit of analysis (occupation versus job/task bundle), methodology, and risk threshold. Their spread is evidence that the headline percentage is method-dependent, not proof that one study simply disproved another.

## Verification result

**The claim “Frey and Osborne predicted that 47% of US jobs would be lost” is misleading.**

A defensible formulation is:

> Frey and Osborne estimated that occupations accounting for about 47% of US employment fell into their high-risk category for potential computerisation, based on their occupation-level model and a 0.7 threshold. They did not forecast that 47% of jobs would actually disappear, nor specify a reliable date by which that would happen.

The Oxford Martin headline's “to be lost” framing is stronger than the paper's carefully bounded conclusion. The paper itself uses “at risk” and explicitly disclaims an estimate of actual job losses.

## Incremental value observed from Verification Integrity

The skill's relevant contribution here was not merely checking whether 47% appears in the paper. It required checking **what the percentage counts**, the threshold used, the time horizon, and the authors' explicit limitations. It also required resisting the temptation to treat other headline estimates as direct rebuttals without reconciling their methods and populations.

This changes the answer materially: the number is real, but the common “47% of jobs will be lost” interpretation is not what the study established.

## Limits

- This audit checks how the original estimate is represented; it does not independently reproduce the Frey–Osborne model or validate its predictions.
- The ONS article is a useful official methodological comparison, but its summary of other studies is not a substitute for independently auditing every underlying study.
- The test does not establish which automation-risk model is most accurate.

## Verification status

- **Inspected:** original research paper, Oxford Martin public-facing news item, and ONS methodological comparison.
- **Checked:** unit of analysis, high-risk threshold, time horizon, explicit limitations, and differences between estimates.
- **Conclusion:** headline interpretation rejected as overstated; qualified 47% estimate retained.
- **Delivered:** this test record to the cognitive-skills repository.
- **No user project repositories modified.**

[Verification Integrity used]
