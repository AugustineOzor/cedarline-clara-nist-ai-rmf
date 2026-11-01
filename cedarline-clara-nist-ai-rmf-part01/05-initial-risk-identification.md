# Initial Risk Identification: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 02: Map](../README.md) › Document 5 of 5
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIM-RSK-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Facilitated by** | AI Governance Office |
| **Date** | 31 October 2026 |

## 1. Purpose

This document brings together the risks found while mapping CLARA: in the system profile, the impact assessment, the requirements work and the third-party review. It is the hand-over from **Map** to **Measure**: each risk here becomes an entry in the AI risk register in Part 03, where it is scored against test evidence and given a treatment plan.

## 2. Sources

| Source | Risks contributed |
| --- | --- |
| AI System Profile (CB-AIM-PRF-001) | Known limits, scope and misuse |
| AI Impact Assessment (CB-AIM-AIA-001) | Harms to people and groups |
| Trustworthiness Requirements (CB-AIM-REQ-001) | Risks of not meeting a requirement |
| Third-Party Component Register (CB-AIM-TPC-001) | Supplier and dependency risks |
| Risk workshop, 29 October 2026 | Operational, security and change risks |

## 3. Identified risks

| Risk ID | Risk | Category | Linked to | Proposed owner |
| --- | --- | --- | --- | --- |
| R-01 | Model is less accurate than expected on new applicants, causing wrong approvals or declines | Validity | IA-01; REQ-VR-01 to 03 | Head of Credit Risk Analytics |
| R-02 | Features act as proxies for nationality or gender, producing unfair outcomes | Fairness | IA-02; REQ-FR-02, 03 | Head of Credit Risk Analytics |
| R-03 | Applicants with thin credit files are systematically disadvantaged | Fairness | IA-03; REQ-FR-05 | Head of Retail Credit Operations |
| R-04 | Historical approval bias is learned from the training data | Fairness | IA-05 | Head of Credit Risk Analytics |
| R-05 | Reason codes do not reflect the real drivers of a decision | Explainability | IA-06; REQ-EX-02 | Head of Credit Risk Analytics |
| R-06 | Customers cannot understand or challenge decisions | Transparency | IA-06; REQ-EX-03 | Head of Compliance |
| R-07 | Reviewers rely on CLARA without real scrutiny (automation bias) | Human oversight | IA-07; REQ-HO-01, 02 | Head of Retail Credit Operations |
| R-08 | Model performance drifts after an economic shock | Validity | IA-08; REQ-VR-02 | Head of Credit Risk Analytics |
| R-09 | CLARA is used outside its intended purpose | Governance | IA-09 | Head of AI Governance |
| R-10 | Personal data is over-collected, misused or breached | Privacy and security | IA-10; REQ-PR-01 to 04 | Data Protection Officer |
| R-11 | Bureau or verification data is wrong or unavailable | Third party | IA-11; TPC-01 to 03 | Procurement and Third-Party Risk |
| R-12 | Supplier changes its method without notice, shifting CLARA's results | Third party | TPC-03 | Procurement and Third-Party Risk |
| R-13 | Model artefacts or pipeline tampered with, or a vulnerable library exploited | Security | REQ-SR-01, 02; TPC-05 to 07 | CISO |
| R-14 | Inputs manipulated to obtain approval (gaming) | Security | REQ-SR-03 | CISO |
| R-15 | Decision logs are incomplete, so decisions cannot be reconstructed for regulators or complaints | Accountability | REQ-AT-01 | Head of Credit Risk Analytics |
| R-16 | EU go-live slips past 2 December 2027, or conformity assessment is incomplete | Regulatory | OB-10; OB-11 | Head of AI Governance |
| R-17 | Platform outage prevents decisions, and the fallback fails | Resilience | REQ-SF-02; TPC-04 | Head of Credit Risk Analytics |
| R-18 | Thresholds or decision routing are configured incorrectly | Safety | REQ-SF-01 | Head of Retail Credit Operations |

## 4. Next steps

1. **Part 03 (Measure):** test each risk against the requirements, score it and record it in the AI risk register.
2. Confirm owners at the November AI Governance Committee meeting.
3. Revisit this list after testing, and add any new risks found.

## Framework mapping

| This document | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Risk identification from mapping | MAP 5.1; MAP 4.1 | Clause 6.1.2 | Art. 9(2)(a) |
| Hand-over to measurement | MEASURE 1.1 | Clause 8.2 | Art. 9(2)(b) |

<!-- nav -->
---

[← Previous: Third-Party Component Register: CLARA](04-third-party-component-register.md) &nbsp;|&nbsp; [Part 02: Map](../README.md) &nbsp;|&nbsp; [Next: Part 03: Measure →](../../03-measure/README.md)
<!-- /nav -->
