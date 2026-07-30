# STROBE-MR Checklist

**Study Title:** Genetic evidence for bidirectional associations between major depressive disorder and anxiety disorders: a bidirectional Mendelian randomization and functional annotation study

**Authors:** Chen Chao, Zehui Chen, Yangang Wang, Jinsheng Zeng, Xinyu Hao, Ningning Ren

**Journal:** Journal of Affective Disorders

**Date:** 2026-07-28

---

## Instructions

The STROBE-MR (Strengthening the Reporting of Observational Studies in Epidemiology using Mendelian Randomization) checklist contains 22 items. Each item should be addressed in the manuscript. This document maps each STROBE-MR item to the relevant section of our manuscript.

---

## STROBE-MR Checklist Items

### TITLE and ABSTRACT

| Item | Recommendation | Manuscript Section |
|------|---------------|-------------------|
| **1** | **Indicate Mendelian randomization (MR) as the study type in the title and/or abstract.** | **Title:** "...a bidirectional Mendelian randomization and functional annotation study". **Abstract Methods:** "We performed bidirectional two-sample Mendelian randomization..." |
| **2** | **Provide an informative and balanced summary of what was done and what was found in the abstract.** | **Abstract:** Structured abstract with Background, Methods, Results, Limitations, and Conclusions, including instrument strength (F-statistics), Steiger directionality tests, bidirectional estimates, MVMR, LDSC, colocalization, and functional annotation. |

---

### INTRODUCTION

| Item | Recommendation | Manuscript Section |
|------|---------------|-------------------|
| **3** | **Explain the scientific rationale for the MR study, including: (a) why MR is a helpful method to address the study question; (b) rationale for the selected exposures and outcomes; and (c) rationale for the selected genetic instruments.** | **Section 1, paragraphs 2-3:** (a) MR reduces confounding and reverse causation; (b) MDD and anxiety disorders are highly comorbid with unclear directionality; (c) the latest large-scale PGC GWAS provide strong genetic instruments. |
| **4** | **Describe the causal hypothes(es) being tested, including which exposure(s) influence which outcome(s), and specify the direction of the hypothesized effect.** | **Section 1, final paragraph:** four pre-specified aims covering bidirectional associations between MDD and anxiety disorders, formal directionality testing, sample-overlap and ancestry-matching evaluation, and shared-mechanism exploration. |
| **5** | **State that the MR study and its results should be viewed as an investigation of potentially causal relationships rather than definitive proof of causality.** | **Throughout:** consistent use of "putative", "genetic evidence for", and "suggests"; explicit cautionary language in the Abstract Limitations and Section 4.1. |

---

### METHODS

| Item | Recommendation | Manuscript Section |
|------|---------------|-------------------|
| **6** | **State the source of data for the MR analyses. If relevant, state that a systematic review of identified studies was performed to select data sources.** | **Section 2.2:** European-ancestry subset (excluding 23andMe) of the PGC 2025 depression GWAS; PGC 2026 anxiety GWAS; IEU OpenGWAS for covariates. No systematic review was performed; the largest available ancestry-matched GWAS were selected. |
| **7** | **Provide full details on how genetic instruments were selected, including: (a) instrument selection algorithm; (b) number of instruments; (c) method of accounting for linkage disequilibrium; (d) genetic instrument strength, such as expected F statistics or R²; and (e) allele frequencies if available.** | **Sections 2.2-2.4:** (a) P < 5 x 10^-8; (b) 198 MDD and 50 anxiety instruments after harmonisation; (c) PLINK v1.9 clumping with 1000 Genomes Phase 3 EUR (r2 < 0.001, 10,000 kb); (d) F-statistics reported (mean F = 44.0, range 29.6-118.1 for MDD; mean F = 37.9, range 29.9-59.8 for anxiety; all F > 10); (e) EAF taken from the GWAS and used in QC (0.01-0.99). |
| **8** | **Describe all MR estimators used and state the rationale for their selection.** | **Section 2.4:** IVW (primary), MR-Egger (directional pleiotropy), weighted median/mode and simple mode (robust), MR-PRESSO and Radial MR (outliers), MR-RAPS (robust to weak-instrument and overlap-related inflation). Rationale stated for each. |
| **9** | **Describe all statistical methods and their underlying assumptions, including: (a) methods to evaluate pleiotropy and related assumptions; (b) methods to evaluate sample overlap; (c) methods to evaluate and/or correct for weak instruments; and (d) any other relevant assumptions.** | **Sections 2.4-2.6:** (a) MR-Egger intercept, MR-PRESSO, Radial MR, funnel plots; (b) formal overlap correction with MRlap (cross-trait LDSC intercept lambda = 0.256, SE = 0.009), strong instruments (all F >> 10), MR-RAPS; (c) F-statistics with F < 10 pre-specified as weak; (d) standard IVW/MR assumptions (relevance, independence, exclusion restriction). |
| **10** | **Describe any sample restrictions and justify them.** | **Sections 2.2-2.3:** EAF 0.01-0.99, autosomal variants only, palindromic-variant handling; European-ancestry restriction of both GWAS justified by ancestry matching and data availability. |
| **11** | **Describe any pre-specified analyses, including: (a) primary and secondary analyses; (b) sensitivity analyses; (c) subgroup analyses; (d) effect measure modifiers; (e) statistical methods for multiple testing; and (f) any other pre-specified analyses.** | **Sections 2.4-2.6:** (a) primary IVW; (b) robust estimators, MR-RAPS, Steiger directionality tests, ancestry-matched (European-specific MDD) analysis; (c) none; (d) none; (e) no multiple-testing correction for the two primary MR tests; nominal thresholds with exploratory labeling for annotation; (f) MVMR, LDSC, colocalization, drug-target and cell-type interpretation. |
| **12** | **Describe any methods used to assess or address violations of MR assumptions (e.g., horizontal pleiotropy, dynastic effects, population stratification).** | **Sections 2.4-2.6:** horizontal pleiotropy: MR-Egger intercept, MR-PRESSO, Radial MR, weighted median; population stratification: European LD reference and ancestry-matched datasets; dynastic effects: not directly testable with summary data, acknowledged in Section 4.1. |
| **13** | **Describe any statistical methods used to account for sample structure (e.g., through genomic control, linear mixed models, or other approaches).** | **Section 2.2:** original GWAS applied genomic control / mixed models; all reference-based steps used the 1000 Genomes European panel. |
| **14** | **If a multivariable MR or factorial MR analysis was performed, provide full details on the additional genetic variants and exposures included, and the statistical methods used.** | **Section 2.5:** MVMR conditioning on BMI, education, and smoking initiation; conditional F-statistics reported (24.7 and 20.0); full models in Table 3 and Supplementary Table S7. |
| **15** | **If any Mendelian randomization analyses were performed using individual participant data, describe: (a) the sampling strategy; (b) the number of participants and observations; (c) the method of data collection; and (d) any inclusion and exclusion criteria.** | **Not applicable:** summary-level GWAS data only. |

---

### RESULTS

| Item | Recommendation | Manuscript Section |
|------|---------------|-------------------|
| **16** | **Report the number of individuals and number of cases and controls, as applicable, who were included in the GWAS from which genetic instruments were obtained.** | **Section 2.2 and Table 1:** MDD up to 412,305 cases / 1,588,397 controls (European ancestry, no 23andMe); anxiety up to 122,083 cases / 729,602 controls. |
| **17** | **Report the strength of each genetic instrument.** | **Sections 2.4 and 3.1, Table 1 note:** per-variant F-statistics computed as beta^2/SE^2; MDD mean F = 44.0 (range 29.6-118.1), anxiety mean F = 37.9 (range 29.9-59.8); no instrument with F < 10. |
| **18** | **Report the MR estimates for each analysis conducted.** | **Tables 2-3, Sections 3.1-3.2:** beta, SE, OR, 95% CI, and P values reported for IVW, MR-Egger, weighted median, weighted mode, and simple mode in both directions, and for full MVMR models. |
| **19** | **Report the assessment of the validity of MR assumptions, such as: (a) tests for pleiotropy; (b) reports of sample overlap; (c) Cochran's Q statistic and I²; (d) leave-one-out analyses; and (e) other relevant statistics.** | **Sections 3.1 and 4.1:** (a) MR-Egger intercepts (P = 0.864; P = 0.006), MR-PRESSO; (b) participant overlap formally corrected with MRlap (corrected estimates not attenuated, P < 1 x 10^-37); (c) Cochran's Q heterogeneity assessed; (d) leave-one-out in Supplementary Figures S1-S3; (e) Steiger directionality tests (P = 0.018 and P = 1.9 x 10^-95). |
| **20** | **Report any additional analyses (e.g., sensitivity analyses, subgroup analyses, or effect measure modification analyses) and their results.** | **Sections 3.1-3.4:** ancestry-matched European-specific MDD analysis; MVMR; LDSC genetic correlation; colocalization; exploratory FUMA/MAGMA/eQTL annotation with drug-target and cell-type interpretation. |
| **21** | **Report any evidence of violations of the assumptions underlying the MR analyses and describe the likely direction of bias.** | **Sections 3.1, 4 and 4.1:** anxiety-to-MDD directional pleiotropy (Egger intercept P = 0.006, likely inflating the reverse estimate); participant overlap would bias estimates toward the observational association; liability-scale scaling and winner's curse inflate apparent magnitudes. |
| **22** | **Describe any cases of known or suspected overlapping samples between the exposure and outcome GWAS.** | **Sections 2.2, 2.4 and 4.1:** both GWAS are PGC meta-analyses sharing contributing cohorts; cross-trait LDSC intercept lambda = 0.256 (SE = 0.009) confirms non-trivial overlap; MRlap-corrected estimates were slightly larger than observed in both directions, excluding overlap as an explanation of the associations. |

---

## Additional Reporting Items

### Data Availability and Code

| Item | Status | Details |
|------|--------|---------|
| Data availability statement | **Reported** | GWAS summary statistics from PGC and IEU OpenGWAS (URLs provided). |
| Code availability | **Reported** | Full analysis pipeline deposited in a public GitHub repository (link to be activated upon acceptance); processed tables in the Supplementary Material. |
| Software versions | **Reported** | PLINK v1.9; R with TwoSampleMR, MendelianRandomization, MR-PRESSO, and coloc packages. |

### Ethics and Funding

| Item | Status | Details |
|------|--------|---------|
| Ethics approval | **Reported** | No new individual-level data; original studies obtained approval and consent. |
| Funding | **Reported** | NSFC Grant 82405293. |
| Competing interests | **Reported** | None declared. |

---

## Compliance Summary

| Category | Items | Compliant | Notes |
|----------|-------|-----------|-------|
| Title and Abstract | 2 | 2/2 | ✓ |
| Introduction | 3 | 3/3 | ✓ |
| Methods | 10 | 10/10 | ✓ (Item 15 N/A) |
| Results | 7 | 7/7 | ✓ |
| **Total** | **22** | **22/22** | **Fully compliant** |

---

## Sign-off

This checklist was completed by the corresponding authors to ensure full compliance with STROBE-MR reporting guidelines. All 22 items have been addressed in the manuscript.

**Completed by:** _________________________ **Date:** _______________

---

## References

Skrivankova, V.W., Richmond, R.C., Woolf, B.A.R., et al., 2021. Strengthening the reporting of observational studies in epidemiology using Mendelian randomization: the STROBE-MR statement. JAMA 326, 1614-1621.
