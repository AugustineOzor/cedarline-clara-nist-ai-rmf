# Test and Evaluation Results Report: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 03: Measure](../README.md) › Document 2 of 4
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMS-TER-001 |
| **System** | AI-CR-001 CLARA, model version 1.2 |
| **Version** | 1.0 |
| **Prepared by** | Model Risk Management, with Credit Risk Analytics |
| **Date** | 14 November 2026 |
| **Test plan** | CB-AIMS-TEV-001 |
| **Results by requirement** | `files/CB-AIM-REQ-001_Requirements_Traceability_Matrix_v1.1_results.xlsx` |

## 1. Summary

CLARA version 1.2 is **fit for purpose, with conditions**. It outperforms Scorecard 19 on every performance measure and meets the fairness limits in the risk tolerance statement, after three issues found in first-round testing were fixed and retested.

| Result | Requirements |
| --- | --- |
| **Pass** | 27 |
| **Pass with exception** | 1 (REQ-PR-04, a *Should* requirement) |
| **Open: evidence due before G3** | 3 (REQ-AT-02, REQ-AT-03, REQ-PR-03) |
| **Fail** | 0 |
| **Total** | 31 |

**Issues found and fixed in first-round testing**

| Issue | First result | Fix | Retest |
| --- | --- | --- | --- |
| Grade F over-predicted risk | Predicted 14.0% versus observed 12.3% (+13.8%) | Recalibrated grade boundaries (model v1.1 to v1.2) | Within +4.1%: **Pass** |
| Employer sector acted as a proxy for nationality | Cramér's V 0.41 | Regrouped 38 sectors into 6 broad sectors | 0.22: **Pass** |
| Thin-file expatriate applicants under-approved | Adverse impact ratio 0.76 | Added salary-transfer history and verified rent payments (with consent) for thin-file applicants | 0.83: **Pass** (amber, monitored monthly) |

Three further items were fixed during testing: a high-severity vulnerability in a software dependency, missing reviewer comments in 2% of logged manual reviews, and the Arabic version of the decline letter, which customers found harder to understand.

## 2. Performance (T-01 to T-04)

Out-of-time sample: 47,800 applications approved January to June 2025.

| Measure | Scorecard 19 | CLARA v1.2 | Criterion | Result |
| --- | --- | --- | --- | --- |
| Gini (overall) | 0.47 | **0.58** | At least 0.55 and above Scorecard 19 | Pass |
| KS statistic | 0.35 | 0.44 | Reported only | n/a |
| Gini: Qatar / EU | 0.48 / 0.44 | 0.59 / 0.55 | At least 0.50 | Pass |
| Gini: new to bank / existing customers | 0.41 / 0.52 | 0.52 / 0.61 | At least 0.50 | Pass |
| Gini: personal loans / credit cards | 0.46 / 0.48 | 0.57 / 0.58 | At least 0.50 | Pass |
| PSI, shadow pilot versus development | n/a | 0.06 | Below 0.10 | Pass |

### Calibration by grade (after recalibration)

| Grade | Predicted default rate | Observed default rate | Difference | Result |
| --- | --- | --- | --- | --- |
| A | 0.4% | 0.4% | 0% | Pass |
| B | 1.0% | 1.0% | 0% | Pass |
| C | 2.3% | 2.4% | −4.2% | Pass |
| D | 4.6% | 4.8% | −4.2% | Pass |
| E | 7.9% | 7.6% | +3.9% | Pass |
| F | 12.8% | 12.3% | +4.1% | Pass |
| G | 24.5% | 25.9% | −5.4% | Pass |

## 3. Safety and routing (T-05, T-06)

| Test | Result |
| --- | --- |
| 1,240 scripted cases across all grades, amounts and products | 1,240 of 1,240 routed correctly: **Pass** |
| Thin-file applicants (212 cases) | All referred; none auto-approved or auto-recommended for decline: **Pass** |
| Simulated CLARA outage, verification outage and bureau outage | All applications fell back to Scorecard 19 with manual review; no automatic approvals: **Pass** |
| 40 out-of-range inputs (for example negative income, impossible dates) | All referred with an alert: **Pass** |

## 4. Fairness (T-07 to T-10)

Favourable outcome: not recommended for decline. Adverse impact ratio (AIR) = favourable rate of the group ÷ favourable rate of the reference group.

| Attribute | Group compared with reference | AIR | Band | Result |
| --- | --- | --- | --- | --- |
| Gender | Women vs men | 0.96 | Green | Pass |
| Age | 18 to 25 vs 41 to 60 | 0.86 | Amber | Pass |
| Age | Over 60 vs 41 to 60 | 0.93 | Green | Pass |
| Nationality (Qatar) | Expatriate vs Qatari national | 0.84 | Amber | Pass |
| Nationality (Ireland) | Non-EU vs Irish | 0.88 | Amber | Pass |
| **Intersection** | **Thin-file expatriates vs reference** | **0.76 → 0.83** | **Red → Amber** | **Fail → Pass after fix** |

| Test | Result |
| --- | --- |
| Equal opportunity difference (largest gap: age 18 to 25) | 3.8 percentage points: Amber, **Pass** (limit 5) |
| Proxy analysis: 31 features | One feature above 0.30 (employer sector, 0.41); regrouped to 0.22. All features now below 0.30: **Pass** |
| Historical bias check on 22,400 declined applicants | Previously declined expatriates repaid other lenders at rates similar to approved applicants with the same CLARA grade. CLARA does not over-penalise them beyond their observed risk. |

**Interpretation.** Testing whole groups alone would have missed the most serious issue: the gap appeared only for expatriates who were also new to credit. Intersectional testing is now a permanent part of monitoring (see the Measurement Effectiveness Review).

## 5. Explainability (T-11, T-12)

| Test | Result |
| --- | --- |
| Reason codes on referrals and recommended declines (out-of-time sample) | 100% coverage: **Pass** |
| Fidelity: top reason code matches largest SHAP contribution (500 cases) | 98.6%: **Pass** |
| Customer comprehension, English (31 participants) | 87% understood the main reason and how to request a review: **Pass** |
| Customer comprehension, Arabic (30 participants) | First version 76%; after rewording three reason codes and simplifying the review instructions, 84%: **Pass** |

## 6. Security and resilience (T-13 to T-15)

| Test | Result |
| --- | --- |
| Penetration test of the scoring API and review screens | Two high findings (session timeout; missing rate limit on one endpoint). Both fixed and retested: **Pass** |
| Dependency scan | One high-severity vulnerability in an indirect dependency; upgraded and re-scanned clean: **Pass** |
| Model artefact integrity | Artefacts signed; only the MLOps pipeline can write to the model registry: **Pass** |
| Perturbation: income ±5% | 0.9% of decisions changed, all at grade boundaries as expected; no unexpected flips: **Pass** |
| Repeated applications with altered inputs | Blocked after three applications in 30 days; alert raised: **Pass** |
| Availability during shadow pilot | 99.7%: **Pass** |
| Failover drill | Fallback to Scorecard 19 in 3 minutes 40 seconds: **Pass** |

## 7. Accountability, privacy and human oversight (T-16 to T-18)

| Requirement | Result |
| --- | --- |
| REQ-AT-01 Logging | First check: 196 of 200 decisions fully reconstructable; reviewer comments missing in 4 manual reviews. Fixed; retest 200 of 200: **Pass** |
| REQ-AT-02 Technical documentation | 14 of 17 Annex IV items complete: **Open**, due 30 June 2027 |
| REQ-AT-03 Instructions for use | Draft under review: **Open**, due 31 July 2027 |
| REQ-AT-04 AI notice to customers | Notice present in all journeys and letters: **Pass** |
| REQ-PR-01 Feature justification | All 31 features justified in the data governance record: **Pass** |
| REQ-PR-02 Separation of protected data | Separate environment confirmed; no access path from scoring pipeline: **Pass** |
| REQ-PR-03 DPIA | In progress with the DPO: **Open**, due 28 February 2027 |
| REQ-PR-04 Retention | Retention rules designed and approved; automated deletion not yet run in production: **Pass with exception**, confirm three months after go-live |
| REQ-HO-01 to 04 Human oversight | Override with mandatory reason, full review screen, stop function (all automatic approvals switched off in 9 minutes) and training-gated access all demonstrated: **Pass** |

## 8. Validation opinion

Model Risk Management's opinion is that CLARA v1.2 is **fit for purpose, with conditions**:

1. The three open items (REQ-AT-02, REQ-AT-03, REQ-PR-03) must be closed before the G3 go-live decision.
2. The thin-file expatriate segment (AIR 0.83) and age 18 to 25 segment (AIR 0.86) must be monitored monthly, with a target of 0.90 within 12 months of go-live.
3. The override rate cannot be measured in shadow mode. It must be reported weekly for the first three months after go-live.
4. Revalidation is required after 12 months, or earlier if a red limit is reached.

## Framework mapping

| This report | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Performance and validity | MEASURE 2.3; MEASURE 2.5 | A.6.2.4 | Art. 15(1) to (3) |
| Fairness and bias | MEASURE 2.11 | A.7.4 | Art. 10(2)(f), (g) |
| Security and resilience | MEASURE 2.6; MEASURE 2.7 | A.6.2.4 | Art. 15(4), (5) |
| Explainability and transparency | MEASURE 2.8; MEASURE 2.9 | A.8.2 | Art. 13; Art. 86 |
| Privacy | MEASURE 2.10 | A.7.5 | Art. 10(5) |
| Documented results | MEASURE 2.1; MEASURE 4.2 | Clause 9.1 | Art. 11; Annex IV(4) |

<!-- nav -->
---

[← Previous: Test, Evaluation, Verification and Validation Plan: CLARA](01-test-and-evaluation-plan.md) &nbsp;|&nbsp; [Part 03: Measure](../README.md) &nbsp;|&nbsp; [Next: AI Risk Register: CLARA →](03-ai-risk-register.md)
<!-- /nav -->
