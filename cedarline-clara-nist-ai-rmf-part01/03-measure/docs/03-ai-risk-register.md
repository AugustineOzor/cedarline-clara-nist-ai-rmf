# AI Risk Register: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 03: Measure](../README.md) › Document 3 of 4
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMS-RR-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 (after validation, 14 November 2026) |
| **Owner** | Head of Credit Risk Analytics |
| **Reviewed by** | AI Governance Office; Model Risk Management |
| **Full register** | `files/CB-AIMS-RR-001_AI_Risk_Register.xlsx` |

## 1. Purpose

This is the living list of CLARA's risks. It takes the 18 risks identified in Part 02 (CB-AIM-RSK-001), scores each one before and after controls using the test evidence in the results report (CB-AIMS-TER-001), and records the treatment decision. Risks that remain above tolerance carry into the risk treatment plan in Part 04.

## 2. Scoring

**Likelihood** (1 rare to 5 almost certain) × **Impact** (1 minimal to 5 severe) = score out of 25.

| Score | Rating | Required response |
| --- | --- | --- |
| 15 to 25 | **Critical** | Not accepted for a Tier 1 system. Must be reduced before go-live. |
| 11 to 14 | **High** | Treatment plan and AI Governance Committee oversight |
| 7 to 10 | **Medium** | Treatment plan; monitored by the system owner |
| 1 to 6 | **Low** | Accepted with routine monitoring |

## 3. Register

| Risk | Description | Inherent L × I | Inherent | Key controls and evidence | Residual L × I | Residual | Decision | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | Model less accurate than expected | 3 × 4 = 12 | High | Gini 0.58; all segments at least 0.52; recalibrated (T-01 to T-03) | 2 × 4 = 8 | Medium | Mitigate | Head of Credit Risk Analytics |
| R-02 | Proxies for nationality or gender | 3 × 5 = 15 | Critical | Protected attributes and postcode excluded; employer sector regrouped (T-09: all features below 0.30) | 2 × 4 = 8 | Medium | Mitigate | Head of Credit Risk Analytics |
| R-03 | Thin-file applicants disadvantaged | 4 × 4 = 16 | Critical | Always referred; alternative data added; AIR 0.76 → 0.83 (T-07) | 3 × 3 = 9 | Medium | Mitigate | Head of Retail Credit Operations |
| R-04 | Historical approval bias learned | 3 × 4 = 12 | High | Reject inference; historical bias check found no over-penalising (T-10) | 2 × 3 = 6 | Low | Accept | Head of Credit Risk Analytics |
| R-05 | Reason codes do not reflect real drivers | 2 × 4 = 8 | Medium | Fidelity 98.6% (T-11) | 1 × 4 = 4 | Low | Accept | Head of Credit Risk Analytics |
| R-06 | Customers cannot understand or challenge | 3 × 3 = 9 | Medium | Comprehension 87% English, 84% Arabic (T-12); human review route | 2 × 2 = 4 | Low | Accept | Head of Compliance |
| R-07 | Automation bias by reviewers | 3 × 4 = 12 | High | Training-gated access; mandatory override reasons (T-17). Override rate not measurable in shadow mode | 2 × 4 = 8 | Medium | Mitigate | Head of Retail Credit Operations |
| R-08 | Drift after an economic shock | 2 × 4 = 8 | Medium | PSI 0.06 (T-04); monthly monitoring; fallback to Scorecard 19 | 2 × 3 = 6 | Low | Accept | Head of Credit Risk Analytics |
| R-09 | Use outside intended purpose | 2 × 4 = 8 | Medium | Scope limits; access controls; change control | 1 × 4 = 4 | Low | Accept | Head of AI Governance |
| R-10 | Personal data over-collected or breached | 2 × 4 = 8 | Medium | Feature justification and data separation (T-18); encryption; DPIA due | 1 × 4 = 4 | Low | Accept | Data Protection Officer |
| R-11 | Supplier data wrong or unavailable | 2 × 3 = 6 | Low | Data-quality checks; outage fallback (T-06) | 2 × 2 = 4 | Low | Accept | Procurement and Third-Party Risk |
| R-12 | Supplier changes method without notice | 3 × 3 = 9 | Medium | 30-day change notice in contract; monthly accuracy sampling | 2 × 3 = 6 | Low | Accept | Procurement and Third-Party Risk |
| R-13 | Tampering or exploited vulnerability | 2 × 5 = 10 | Medium | Penetration test and dependency findings closed; signed artefacts (T-13) | 1 × 5 = 5 | Low | Accept | CISO |
| R-14 | Inputs manipulated to gain approval | 3 × 3 = 9 | Medium | Robustness and repeated-application tests passed (T-14) | 2 × 3 = 6 | Low | Accept | CISO |
| R-15 | Incomplete decision logs | 3 × 4 = 12 | High | Logging fixed; 200 of 200 decisions reconstructed (T-16) | 1 × 4 = 4 | Low | Accept | Head of Credit Risk Analytics |
| R-16 | EU deadline missed or conformity incomplete | 3 × 5 = 15 | Critical | Plan in place; but technical documentation, instructions for use and DPIA still open | 2 × 5 = 10 | Medium | Mitigate | Head of AI Governance |
| R-17 | Outage and failed fallback | 2 × 4 = 8 | Medium | Failover in 3 minutes 40 seconds (T-15) | 1 × 3 = 3 | Low | Accept | Head of Credit Risk Analytics |
| R-18 | Thresholds or routing misconfigured | 2 × 4 = 8 | Medium | 1,240 of 1,240 routing tests passed (T-05); configuration change control | 1 × 4 = 4 | Low | Accept | Head of Retail Credit Operations |

## 4. Risk profile

| Rating | Inherent | Residual |
| --- | --- | --- |
| Critical | 3 | **0** |
| High | 4 | **0** |
| Medium | 10 | **5** |
| Low | 1 | **13** |

**No Critical or High risks remain.** Five risks remain **Medium** and go into the risk treatment plan in Part 04: R-01 (accuracy), R-02 (proxies), R-03 (thin-file applicants), R-07 (automation bias) and R-16 (EU readiness). R-03 is the highest at 9.

## 5. Acceptance

The 13 Low residual risks are accepted by their owners, within the AI Risk Tolerance Statement. Acceptance of the five Medium risks depends on the treatment plan being approved by the AI Governance Committee at the G3 go-live decision.

## Framework mapping

| This register | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Risks scored with evidence | MEASURE 1.1; MEASURE 2.13 | Clause 6.1.2; 8.2 | Art. 9(2)(b), (c) |
| Prioritisation and response decisions | MANAGE 1.2; MANAGE 1.3 | Clause 6.1.3; 8.3 | Art. 9(2)(d); 9(5) |
| Residual risk accepted by owners | MANAGE 1.4 | Clause 8.3 | Art. 9(5) |

<!-- nav -->
---

[← Previous: Test and Evaluation Results Report: CLARA](02-test-and-evaluation-results.md) &nbsp;|&nbsp; [Part 03: Measure](../README.md) &nbsp;|&nbsp; [Next: Measurement Effectiveness Review: CLARA →](04-measurement-effectiveness-review.md)
<!-- /nav -->
