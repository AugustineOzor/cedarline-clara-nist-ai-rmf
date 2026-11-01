# Part 03: Measure

<!-- nav -->
[Repository home](../README.md) › Part 03: Measure
<!-- /nav -->

**NIST AI RMF function: MEASURE.** This part tests CLARA against the 31 requirements from Part 02, records what passed, what failed and how failures were fixed, scores every risk using that evidence, and checks whether the measures themselves were good enough.

## Documents

| # | Document | ID | What it does | Files |
| --- | --- | --- | --- | --- |
| 1 | [Test, Evaluation, Verification and Validation Plan](docs/01-test-and-evaluation-plan.md) | CB-AIMS-TEV-001 | 18 tests across performance, fairness, explainability, security, logging and human oversight, with test data, pass criteria and independent roles | Word |
| 2 | [Test and Evaluation Results Report](docs/02-test-and-evaluation-results.md) | CB-AIMS-TER-001 | Results for every test, three first-round failures and their fixes, and Model Risk Management's validation opinion | Word, Excel |
| 3 | [AI Risk Register](docs/03-ai-risk-register.md) | CB-AIMS-RR-001 | 18 risks scored before and after controls, with a heat map and treatment decisions | Word, Excel |
| 4 | [Measurement Effectiveness Review](docs/04-measurement-effectiveness-review.md) | CB-AIMS-MER-001 | What the metrics captured, what they missed, and the changes made before production monitoring | Word |

## Highlights

- **Realistic results.** Three tests failed first time: grade F calibration, employer sector acting as a proxy for nationality, and approval rates for thin-file expatriate applicants. Each was fixed and retested, with both results recorded.
- **Intersectional fairness.** Group-level results passed, but the issue for thin-file expatriates appeared only when nationality and credit history were tested together. That lesson now shapes monitoring.
- **Clear validation opinion.** CLARA v1.2 is "fit for purpose, with conditions": 28 of 31 requirements met, 3 open items that must close before go-live, and no failures.
- **Risk profile reduced.** Three Critical and four High inherent risks are reduced to five Medium and thirteen Low residual risks. The five Medium risks go to the treatment plan in Part 04.
- **Working spreadsheets.** The risk register calculates scores and ratings from likelihood and impact and builds a heat map automatically. The traceability matrix (v1.1) now records every test result.

## NIST AI RMF coverage

| Subcategory | Covered by |
| --- | --- |
| MEASURE 1.1 to 1.3 Methods, metrics and independent assessment | Test plan |
| MEASURE 2.1 to 2.13 Trustworthiness characteristics evaluated | Results report |
| MEASURE 3.1 Tracking risks over time | Risk register; measurement review |
| MEASURE 4.1 to 4.3 Effectiveness of measurement | Measurement effectiveness review |

<!-- nav -->
---

[← Previous: Initial Risk Identification: CLARA](../02-map/docs/05-initial-risk-identification.md) &nbsp;|&nbsp; [Repository home](../README.md) &nbsp;|&nbsp; [Next: Test, Evaluation, Verification and Validation Plan: CLARA →](docs/01-test-and-evaluation-plan.md)
<!-- /nav -->
