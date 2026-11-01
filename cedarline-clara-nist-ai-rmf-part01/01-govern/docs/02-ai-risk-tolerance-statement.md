# AI Risk Tolerance Statement

<!-- nav -->
[Repository home](../../README.md) › [Part 01: Govern](../README.md) › Document 2 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIG-RTS-001 |
| **Version** | 1.0 |
| **Owner** | Chief Risk Officer |
| **Approved by** | Board Risk Committee, 24 September 2026 |
| **Next review** | September 2027, or when a review trigger in section 6 occurs |

## 1. Purpose

This statement sets how much AI risk Cedarline Bank is willing to accept in pursuit of its goals, and turns that into measurable limits. It is the reference point for every AI risk assessment, go/no-go decision and monitoring alert.

## 2. How this tolerance was set

The Board Risk Committee set these levels after considering:

- the bank's overall risk appetite statement, especially its low appetite for conduct and regulatory risk;
- the potential harm to customers from wrong or unfair credit decisions;
- regulatory expectations under the EU AI Act, GDPR, the EU Consumer Credit Directive and Qatar Central Bank requirements;
- the performance of the existing Scorecard 19, which sets the minimum standard any replacement must beat;
- input from Compliance, the Data Protection Officer, Model Risk Management and Retail Credit Operations.

## 3. Appetite levels

| Level | Meaning |
| --- | --- |
| **Zero** | Not accepted under any circumstances. Any occurrence is escalated immediately. |
| **Low** | Accepted only when the risk is minimal, well controlled and clearly outweighed by the benefit. |
| **Moderate** | Accepted within defined limits when controls and monitoring are in place. |

## 4. Tolerance by risk category

| Risk category | Appetite | Statement |
| --- | --- | --- |
| **Prohibited practices** | Zero | No AI practice prohibited by the EU AI Act, and no use of protected characteristics as model inputs |
| **Unfair discrimination** | Low | AI outcomes must not disadvantage people because of a protected characteristic |
| **Lack of human oversight** | Zero (Tier 1) | No adverse decision about an individual without meaningful human review |
| **Explainability** | Low | Every adverse outcome must be explainable to the customer in plain language |
| **Model performance** | Moderate | Performance may vary within agreed limits but must stay above the previous model |
| **Model stability and drift** | Moderate | Population and score shifts are accepted within limits, with review when limits are reached |
| **Privacy** | Low | Personal data is used only for documented, lawful purposes |
| **Security** | Low | No known critical or high-severity vulnerability in production AI systems |
| **Third-party dependency** | Moderate | Critical AI suppliers are accepted where exit and fallback plans exist |
| **Regulatory non-compliance** | Zero | No known breach of an applicable AI, data protection or consumer credit requirement |

## 5. Measurable limits for Tier 1 credit models

These limits apply to CLARA and any future Tier 1 credit model. **Green** is within tolerance, **amber** triggers investigation by the system owner within 10 working days, and **red** triggers escalation to the AI Governance Committee within 2 working days and may lead to suspension.

| Metric | Green | Amber | Red |
| --- | --- | --- | --- |
| **Gini coefficient** (discrimination power, on out-of-time data) | At least 0.55 | 0.50 to 0.55 | Below 0.50, or below Scorecard 19 |
| **Calibration**: predicted versus observed default rate, per risk grade | Within ±10% | ±10% to ±20% | Beyond ±20% |
| **Population stability index (PSI)** of the score distribution | Below 0.10 | 0.10 to 0.25 | Above 0.25 |
| **Adverse impact ratio**: approval rate of each tested group divided by the reference group's | At least 0.90 | 0.80 to 0.90 | Below 0.80 |
| **Equal opportunity difference**: gap in approval rates among applicants who went on to repay | Up to 3 percentage points | 3 to 5 points | Above 5 points |
| **Explanation coverage**: referrals and recommended declines with valid reason codes | 100% | n/a | Below 100% |
| **Human override rate** of CLARA recommendations | 3% to 15% | 15% to 25%, or below 3% | Above 25% |
| **Complaints about credit decisions** involving CLARA | Below 0.3% of decisions | 0.3% to 0.5% | Above 0.5%, or any upheld discrimination complaint |
| **Critical or high vulnerabilities** open in the CLARA platform | 0 | n/a | 1 or more past its fix deadline |

A human override rate that is **too low** is treated as a warning sign too, because it may mean reviewers are accepting CLARA's recommendations without real scrutiny (automation bias).

## 6. Review triggers

This statement is reviewed at least once a year, and also when:

- a new AI regulation or major amendment applies to the bank;
- a Tier 1 system reaches a red limit, or two amber limits in the same quarter;
- the bank enters a new market or launches a new AI-supported credit product;
- a serious AI incident occurs at Cedarline or at a comparable institution.

## 7. Accountability

The **Chief Risk Officer** owns this statement. **System owners** must report against the limits in section 5 monthly. The **Head of AI Governance** consolidates the results for the AI Governance Committee and, each quarter, for the Board Risk Committee.

## Framework mapping

| This statement | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Appetite and limits | GOVERN 1.3; MAP 1.5 | Clause 6.1.1; 6.1.2 | Art. 9(5) |
| Fairness limits | MEASURE 2.11 | A.7.4 | Art. 10(2)(f), 15 |
| Monitoring and escalation | MANAGE 1.3; MANAGE 4.1 | Clause 9.1 | Art. 72 |

<!-- nav -->
---

[← Previous: AI Governance Policy](01-ai-governance-policy.md) &nbsp;|&nbsp; [Part 01: Govern](../README.md) &nbsp;|&nbsp; [Next: AI Roles and Accountability Matrix →](03-roles-and-accountability.md)
<!-- /nav -->
