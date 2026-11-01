# Test, Evaluation, Verification and Validation Plan: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 03: Measure](../README.md) › Document 1 of 4
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMS-TEV-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Independent reviewer** | Model Risk Management |
| **Approved by** | Model Risk Management, 3 August 2026 |
| **Period** | August to October 2026 |

## 1. Purpose

This plan sets out how CLARA will be tested before the G2 validation gate: what is measured, on which data, by whom, and what counts as a pass. Each test traces to a requirement in the Trustworthiness Requirements Specification (CB-AIM-REQ-001), so the results show exactly which requirements are met.

## 2. Principles

- **Independence.** Model Risk Management (MRM) designs and runs, or re-performs, the validation tests. The development team runs functional tests, and MRM reviews them.
- **Unseen data.** Performance and fairness are measured on data the model never saw during development.
- **Fixed criteria.** Pass criteria come from the requirements specification and the risk tolerance statement, and cannot be changed after results are known.
- **Retest after fixes.** Any failed test is retested after remediation, and both results are recorded.

## 3. Test data

| Dataset | Period | Size | Use |
| --- | --- | --- | --- |
| Development sample | Applications approved January 2020 to December 2023 | 331,000 | Training and tuning only |
| Holdout sample | Random 20% held back from the same period | 81,000 | In-time performance check |
| **Out-of-time sample** | Applications approved January to June 2025, with 12-month outcomes | **47,800** (Qatar 35,100; EU 12,700) | **Main performance and fairness tests** |
| Declined-applicant sample | Declined applications 2023 to 2025 with later bureau outcomes | 22,400 | Reject inference and historical bias checks |
| **Shadow pilot** | Live applications, 4 August to 31 October 2026; CLARA scored in parallel, decisions still made by Scorecard 19 | **14,200** | Stability, routing, operations, logging |
| Synthetic test cases | Designed by MRM and Credit Operations | 1,240 | Routing, edge cases, out-of-range inputs |

**Protected-attribute data** (nationality, gender, age band) is used only for fairness testing. It is held in a separate, access-controlled environment by the fairness testing team, joined to scores by a pseudonymous key, and never available to the scoring pipeline (REQ-PR-02).

## 4. Tests

| Test ID | Test | Method | Data | Requirements | Pass criterion | Performed by |
| --- | --- | --- | --- | --- | --- | --- |
| T-01 | Discrimination power | Gini and KS against Scorecard 19 | Out-of-time | REQ-VR-01 | Gini at least 0.55 and above Scorecard 19 | MRM |
| T-02 | Calibration by grade | Predicted versus observed default rate | Out-of-time | REQ-VR-02 | Within ±10% relative, every grade | MRM |
| T-03 | Segment performance | Gini by market, customer type and product | Out-of-time | REQ-VR-03 | Gini at least 0.50 in each segment | MRM |
| T-04 | Population stability | PSI of score distribution, pilot versus development | Shadow pilot | Tolerance s.5 | PSI below 0.10 | Development |
| T-05 | Decision routing | Scripted cases across grades, amounts and thin files | Synthetic | REQ-SF-01; REQ-VR-04 | 100% routed correctly | Credit Operations; MRM |
| T-06 | Fail-safe and input validation | Simulated outages and out-of-range values | Synthetic; test environment | REQ-SF-02, 03 | Fallback to Scorecard 19; no auto-approval; alerts raised | Development; Operations |
| T-07 | Adverse impact | Adverse impact ratio by group and intersection | Out-of-time | REQ-FR-03; REQ-FR-05 | At least 0.80 for every group (target 0.90) | Fairness testing team; MRM |
| T-08 | Equal opportunity | Gap in favourable-outcome rates among applicants who repaid | Out-of-time | REQ-FR-04 | No more than 5 percentage points | Fairness testing team |
| T-09 | Proxy analysis | Association (Cramér's V) of each feature with protected attributes | Out-of-time | REQ-FR-01, 02 | Below 0.30, or justified and approved | Fairness testing team |
| T-10 | Historical bias | Model outcomes for previously declined applicants versus their later bureau performance | Declined-applicant sample | REQ-FR-03 (supporting) | No group systematically over-penalised | MRM |
| T-11 | Explanation coverage and fidelity | Reason codes present; top code versus largest SHAP contribution | Out-of-time (500-case sample) | REQ-EX-01, 02 | 100% coverage; fidelity at least 98% | MRM |
| T-12 | Customer comprehension | Moderated test of decline letters in English and Arabic | Customer panel | REQ-EX-03 | At least 80% understanding in each language | Customer Experience; Compliance |
| T-13 | Security | Penetration test, dependency scan, artefact integrity check | Test environment | REQ-SR-01, 02 | No open critical or high findings; artefacts signed | Information Security |
| T-14 | Robustness | Small input perturbations; repeated-application gaming | Out-of-time; synthetic | REQ-SR-03 | No unexpected decision flips; rate limits enforced | MRM; Information Security |
| T-15 | Availability and failover | Pilot uptime; failover drill | Shadow pilot | REQ-SR-04 | 99.5% availability; fallback within 5 minutes | Development; Operations |
| T-16 | Logging completeness | Reconstruct 200 decisions from logs alone | Shadow pilot | REQ-AT-01 | 100% reconstructable | Internal Audit (observer); MRM |
| T-17 | Human oversight functions | Demonstrations of override, review screen and stop function | Test environment | REQ-HO-01 to 04 | All functions work as specified; stop within 15 minutes | Credit Operations |
| T-18 | Documentation and privacy inspections | Inspect technical documentation, instructions for use, notices, DPIA, feature justifications, retention design | Documents | REQ-AT-02 to 04; REQ-PR-01, 03, 04 | Complete and approved | Compliance; DPO; AI Governance Office |

## 5. Fairness test design

| Item | Approach |
| --- | --- |
| **Favourable outcome** | Not recommended for decline (approved or referred) |
| **Groups tested** | Gender; age band (18 to 25, 26 to 40, 41 to 60, over 60); nationality group in Qatar (Qatari national, expatriate); nationality group in Ireland (Irish, EU, non-EU) |
| **Reference group** | The group with the highest favourable-outcome rate for each attribute |
| **Intersections** | Nationality group × thin file; gender × age band |
| **Minimum group size** | 500 applications; smaller groups reported but flagged as low confidence |
| **Lawful basis** | Documented in the DPIA; data used only for bias detection and correction (EU AI Act Art. 10(5); GDPR Art. 9(2)(g) as assessed by the DPO) |

## 6. Roles

| Role | Responsibility |
| --- | --- |
| Head of Credit Risk Analytics | Owns the plan; fixes failed items |
| Model Risk Management | Independent validation; final validation opinion at G2 |
| Fairness testing team (inside MRM) | Holds protected-attribute data; runs fairness tests |
| Information Security | Security and robustness tests |
| Credit Operations | Routing and human oversight tests |
| Internal Audit | Observes T-16 and reviews the test process |

## 7. Exit criteria for G2

1. Every *Must* requirement passes, or is open only because its evidence depends on later steps (for example, the final DPIA).
2. No test is in a failed state.
3. MRM issues a validation opinion of "fit for purpose", with or without conditions.

## Framework mapping

| This plan | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Test approach and metrics | MEASURE 1.1; MEASURE 1.3; MEASURE 2.1 | A.6.2.4 | Art. 9(6) to (8) |
| Representative test data | MEASURE 2.1; MEASURE 2.2 | A.7.3; A.7.4 | Art. 10(3) |
| Independent assessment | MEASURE 1.3 | Clause 9.2 | Art. 17(1)(d) |

<!-- nav -->
---

[← Previous: Part 03: Measure overview](../README.md) &nbsp;|&nbsp; [Part 03: Measure](../README.md) &nbsp;|&nbsp; [Next: Test and Evaluation Results Report: CLARA →](02-test-and-evaluation-results.md)
<!-- /nav -->
