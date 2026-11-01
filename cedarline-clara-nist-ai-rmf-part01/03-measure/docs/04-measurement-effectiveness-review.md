# Measurement Effectiveness Review: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 03: Measure](../README.md) › Document 4 of 4
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMS-MER-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Prepared by** | Model Risk Management |
| **Reviewed by** | AI Governance Office; Compliance |
| **Date** | 18 November 2026 |
| **Next review** | Six months after go-live, then every year |

## 1. Purpose

Testing is only as good as the measures used. This review asks whether the metrics used to test CLARA actually captured the risks that matter, what they missed, and what must change before the same metrics are used to monitor CLARA in production (Part 04).

## 2. Metrics in use

| Metric | What it tells us | Formula or method | Known limitations |
| --- | --- | --- | --- |
| **Gini coefficient** | How well CLARA ranks good and bad risks | 2 × AUC − 1 | Says nothing about whether the predicted default *rates* are right |
| **Calibration by grade** | Whether predicted default rates match reality | (Predicted − observed) ÷ observed, per grade | Needs 12 months of outcomes, so it lags |
| **Population stability index (PSI)** | Whether today's applicants look like the training population | Σ (actual% − expected%) × ln(actual% ÷ expected%) across score bands | Detects change in inputs, not whether performance has dropped |
| **Adverse impact ratio (AIR)** | Whether a group is recommended for decline more often | Favourable rate of group ÷ favourable rate of reference group | Group averages can hide problems in sub-groups; ignores whether the outcome was justified by risk |
| **Equal opportunity difference** | Whether applicants who would repay are treated alike across groups | Gap in favourable rates among applicants who repaid | Needs outcomes; only measurable on approved loans |
| **Reason-code fidelity** | Whether explanations reflect the model's real drivers | Share of cases where the top reason code matches the largest SHAP contribution | Checks the top reason only |
| **Override rate** | Whether reviewers exercise real judgement | Overridden recommendations ÷ reviewed recommendations | Too high and too low are both warning signs; cannot be measured in shadow mode |
| **Customer comprehension** | Whether customers understand explanations | Moderated test with scripted questions | Small samples; lab conditions differ from real life |

## 3. What worked

1. **Fixed criteria set in advance.** Pass criteria came from the tolerance statement and requirements, so first-round failures could not be argued away.
2. **Calibration caught what Gini missed.** Grade F passed on ranking but over-predicted risk by 13.8%. Using both metrics was necessary.
3. **Proxy analysis found the employer-sector problem** before it reached customers.
4. **Retesting after every fix** produced a clear record of what changed and why.

## 4. What the measures missed or could miss

| Gap | What happened or could happen | Change made |
| --- | --- | --- |
| **Intersections** | Group-level AIR passed for expatriates (0.84), but thin-file expatriates were at 0.76. The issue was found only because intersectional testing was added to the plan late. | Intersectional slices (nationality × thin file; gender × age band) are now **mandatory** in testing and monthly monitoring |
| **Outcome lag** | Calibration and equal opportunity need 12 months of repayment data, so problems surface late in production. | Add **early-warning indicators**: 3-month and 6-month arrears rates by grade, compared with expected curves |
| **Override rate unmeasured** | Shadow mode cannot show how reviewers will behave with real decisions. | Weekly override reporting for the first three months, with a sample of overrides reviewed for quality |
| **Small comprehension samples** | About 30 participants per language gives limited confidence. | Track complaint themes and requests for human review as an ongoing real-world measure |
| **Single-reason fidelity** | Fidelity checks only the top reason code. | Extend fidelity test to the top two codes at revalidation |
| **Reject outcomes unknown** | Outcomes for people CLARA would decline are only partly visible through bureau data. | Keep the declined-applicant bureau check every six months |

## 5. Measurement quality checks

| Check | Finding |
| --- | --- |
| Independence | MRM re-performed all performance and fairness calculations; results matched development to two decimal places |
| Data integrity | Out-of-time sample reconciled to source systems: 47,800 records, no duplicates, 0.3% with missing bureau data (excluded and reported) |
| Group sizes | All tested groups above 500 applications except non-EU applicants over 60 (184), reported as low confidence |
| Reproducibility | Test code, data versions and results stored in the model registry under version 1.2 |

## 6. Recommendations for Part 04 (Manage)

1. Monitor all metrics in section 2, plus the early-warning arrears indicators and intersectional AIR, monthly.
2. Use the green, amber and red limits in the risk tolerance statement for every metric that has one.
3. Review this measurement approach six months after go-live, using real monitoring data.

## Framework mapping

| This review | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Effectiveness of measurement | MEASURE 1.2; MEASURE 4.1 | Clause 9.1; 10.1 | Art. 9(8) |
| Feedback on measurement gaps | MEASURE 4.2; MEASURE 4.3 | Clause 10.1 | Art. 72(2) |
| Tracking risks over time | MEASURE 3.1 | Clause 9.1 | Art. 72 |

<!-- nav -->
---

[← Previous: AI Risk Register: CLARA](03-ai-risk-register.md) &nbsp;|&nbsp; [Part 03: Measure](../README.md) &nbsp;|&nbsp; [Next: Part 04: Manage →](../../04-manage/README.md)
<!-- /nav -->
