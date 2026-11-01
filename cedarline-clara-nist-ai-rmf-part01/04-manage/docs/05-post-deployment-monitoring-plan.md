# Post-Deployment Monitoring and Continuous Improvement Plan: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 5 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-MON-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Scorecard** | `files/CB-AIMG-MON-001_Monitoring_Scorecard.xlsx` |

## 1. Purpose

Validation shows CLARA worked on past data. Monitoring shows it keeps working on today's applicants. This plan sets what is monitored, how often, against which limits, who acts, and how what is learned feeds back into CLARA. For the EU, it also serves as the **post-market monitoring plan** required for high-risk AI systems.

## 2. Monitoring scorecard

Limits come from the AI Risk Tolerance Statement (CB-AIG-RTS-001). Metrics added after the Measurement Effectiveness Review are marked **new**.

| # | Metric | Frequency | Green | Amber | Red | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| M-01 | Population stability index (score) | Monthly | Below 0.10 | 0.10 to 0.25 | Above 0.25 | Credit Risk Analytics |
| M-02 | Early-warning arrears: 3-month arrears, actual ÷ expected, by grade (**new**) | Monthly | 0.90 to 1.10 | 0.80 to 1.25 | Outside amber | Credit Risk Analytics |
| M-03 | Gini (12-month outcomes) | Quarterly, once outcomes exist | At least 0.55 | 0.50 to 0.55 | Below 0.50 | Model Risk Management |
| M-04 | Calibration: largest deviation by grade | Quarterly, once outcomes exist | Within ±10% | ±10% to ±20% | Beyond ±20% | Model Risk Management |
| M-05 | Adverse impact ratio: lowest group, **including intersections** (**new**) | Monthly | At least 0.90 | 0.80 to 0.90 | Below 0.80 | Fairness testing team |
| M-06 | Equal opportunity difference: largest gap | Quarterly | Up to 3 points | 3 to 5 points | Above 5 points | Fairness testing team |
| M-07 | Proxy check: highest feature association with protected groups | Quarterly | Below 0.30 | 0.30 to 0.35 | Above 0.35 | Model Risk Management |
| M-08 | Explanation coverage | Daily | 100% | n/a | Below 100% | Credit Risk Analytics |
| M-09 | Reason-code fidelity (sample of 200) | Quarterly | At least 98% | 95% to 98% | Below 95% | Model Risk Management |
| M-10 | Override rate | Weekly for 3 months, then monthly | 3% to 15% | 15% to 25%, or below 3% | Above 25% | Retail Credit Operations |
| M-11 | Complaints about CLARA decisions | Monthly | Below 0.3% | 0.3% to 0.5% | Above 0.5%, or any upheld discrimination complaint | Compliance |
| M-12 | Human review requests completed within 5 days | Monthly | At least 95% | 90% to 95% | Below 90% | Retail Credit Operations |
| M-13 | Availability in business hours | Monthly | At least 99.5% | 99.0% to 99.5% | Below 99.0% | Credit Risk Analytics |
| M-14 | Critical or high vulnerabilities past fix deadline | Weekly | 0 | n/a | 1 or more | CISO |
| M-15 | Supplier data quality: Verilytix income mismatch rate in monthly sample | Monthly | Below 2% | 2% to 5% | Above 5% | Procurement and Third-Party Risk |

## 3. What happens at each level

| Result | Action |
| --- | --- |
| **Green** | Reported in the monthly pack |
| **Amber** | System owner investigates within 10 working days and records findings; two ambers in a quarter trigger an AI Governance Committee review |
| **Red** | Raised as an AI incident (S2 or higher) under CB-AIMG-IRP-001; automatic approvals may be paused; committee informed within 2 working days |

## 4. Feedback loops

| Source | How it is used |
| --- | --- |
| Override reasons | Grouped monthly; recurring reasons (for example "verified income higher than bureau") become candidate model improvements |
| Complaints and human review requests | Themes reviewed monthly by Compliance; any fairness theme triggers a targeted test |
| Customer and staff feedback | Quarterly survey of underwriters on usefulness and trust in reason codes |
| Incidents | Post-incident reviews update tests, limits and training |
| Regulatory change | Monthly horizon scanning by Compliance (CB-AIG-REG-001) |

## 5. Change and retraining

| Trigger | Action |
| --- | --- |
| Scheduled | Annual retraining and full revalidation |
| Red limit on M-01 to M-07 | Investigation; retraining or recalibration if the cause is model-related |
| New data source or feature | Proxy test, impact assessment update, revalidation |
| Material change to decision routing | Requirements and routing tests re-run; AIGC approval |

Every change is versioned, validated by Model Risk Management and recorded in the AI System Inventory. Changes that alter the intended purpose or significantly affect performance require a new go/no-go decision and, in the EU, may require a new conformity assessment.

## 6. Reporting

| Report | Audience | Frequency |
| --- | --- | --- |
| Monitoring scorecard | System owner; AI Governance Office | Monthly |
| CLARA performance and fairness pack | AI Governance Committee | Monthly |
| AI risk summary | Board Risk Committee | Quarterly |
| Annual review and revalidation | AI Governance Committee | Yearly |

## Framework mapping

| This plan | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Post-deployment monitoring | MANAGE 4.1; MEASURE 3.1 | Clause 9.1; A.6.2.6 | Art. 72 |
| Continuous improvement | MANAGE 4.2 | Clause 10.1; 10.2 | Art. 9(2)(c); 17(1)(i) |
| Feedback from users and affected people | MEASURE 3.3; MANAGE 4.3 | A.8.3 | Art. 72(2) |

<!-- nav -->
---

[← Previous: AI Incident Response Procedure](04-ai-incident-response-procedure.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: Third-Party AI Contingency Plan: CLARA →](06-third-party-contingency-plan.md)
<!-- /nav -->
