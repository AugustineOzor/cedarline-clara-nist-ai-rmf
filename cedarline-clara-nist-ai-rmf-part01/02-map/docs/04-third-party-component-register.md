# Third-Party Component Register: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 02: Map](../README.md) › Document 4 of 5
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIM-TPC-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics, with Procurement and Third-Party Risk |
| **Date** | 30 October 2026 |
| **Full register** | `files/CB-AIM-TPC-001_Third_Party_Component_Register.xlsx` |

## 1. Purpose

CLARA is built in-house, but it depends on outside data, services and software. This register lists every third-party component inside or around CLARA, what it does, how critical it is, the main risks and the controls in place, as required by the Third-Party AI and Data Policy (CB-AIG-POL-002).

## 2. Criticality scale

- **Critical:** CLARA cannot make a reliable decision without it
- **High:** loss or failure would materially degrade decisions or compliance
- **Medium:** loss or failure is inconvenient but has a workaround

## 3. Register

| ID | Component | Type | Supplier | Role in CLARA | Personal data | Criticality | Key risks | Key controls | Contingency |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TPC-01 | Qatar credit bureau report | Data | Qatar Credit Bureau | Repayment history and existing debts (Qatar) | Yes | Critical | Inaccurate or outdated records; outage | Data-quality checks; applicant correction route; SLA monitoring | Refer affected cases to manual review |
| TPC-02 | Irish credit bureau report | Data | Central Credit Register (Ireland) | Repayment history and existing debts (EU) | Yes | Critical | Inaccurate records; outage | Data-quality checks; correction route | Refer to manual review |
| TPC-03 | Income and employment verification | API service | Verilytix (fictional) | Verified income and employment tenure | Yes | High | Wrong income; outage; data used beyond purpose; change in method without notice | Contract terms (purpose limits, 30-day change notice, 24-hour incident notice); monthly accuracy sampling | Manual income verification; auto-approval suspended for affected cases |
| TPC-04 | Cloud machine learning platform | Platform | Cloud provider | Training, hosting and serving the model | Yes (in transit and at rest) | Critical | Outage; misconfiguration; data residency; concentration | Separate Qatar and EU environments; encryption with bank-managed keys; DORA register of information; resilience testing | Fallback to Scorecard 19 on-premises |
| TPC-05 | XGBoost | Open-source library | XGBoost community (Apache 2.0) | Model training and scoring | No | High | Vulnerabilities; behaviour change between versions | Version pinned; dependency scanning; change validated through G2 | Retain previous signed model and environment |
| TPC-06 | SHAP | Open-source library | SHAP project (MIT) | Feature contributions for reason codes | No | High | Explanation errors after upgrade | Version pinned; reason-code fidelity test (REQ-EX-02) | Previous version retained |
| TPC-07 | scikit-learn | Open-source library | scikit-learn project (BSD-3) | Data preparation and evaluation | No | Medium | Vulnerabilities; version drift | Version pinned; dependency scanning | Previous version retained |
| TPC-08 | DocRead document extraction | AI system (inventory AI-OP-001) | OCR vendor (fictional) | Extracts application data from documents | Yes | Medium | Extraction errors feeding CLARA | Confidence thresholds; low-confidence fields reviewed by staff | Manual data entry |
| TPC-09 | Economic indicators feed | Data | Public statistics sources | Early-warning triggers for monitoring (not a model input) | No | Medium | Delayed or revised data | Used for monitoring only | Manual review of published data |

## 4. Observations

1. **Three components are critical.** The two credit bureaus and the cloud platform cannot easily be replaced at short notice, so each has a documented fallback that sends cases to manual review or to Scorecard 19.
2. **Verilytix is the highest-risk commercial supplier.** It handles personal data, changes in its method could shift CLARA's results without the bank noticing, and it is a smaller company. Its contract includes change notice and audit rights, and its accuracy is sampled monthly.
3. **Open-source components are pinned.** Any upgrade is treated as a model change and goes through validation before release.
4. **AI inside a supplier's product.** DocRead is itself an AI system, so its errors can flow into CLARA. That link is tracked in both inventory entries.

## 5. Review

The register is reviewed every six months and whenever a component, supplier or version changes. Tier 1 suppliers are reassessed every six months under CB-AIG-POL-002.

## Framework mapping

| This register | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act and other |
| --- | --- | --- | --- |
| Third-party components and their risks | MAP 4.1; MAP 4.2; GOVERN 6.1 | A.10.2; A.10.3 | AI Act Art. 25(4); DORA Art. 28 |
| Contingency for supplier failure | GOVERN 6.2; MANAGE 3.1 | A.10.3 | DORA Art. 28(8) |

<!-- nav -->
---

[← Previous: Trustworthiness Requirements Specification: CLARA](03-trustworthiness-requirements.md) &nbsp;|&nbsp; [Part 02: Map](../README.md) &nbsp;|&nbsp; [Next: Initial Risk Identification: CLARA →](05-initial-risk-identification.md)
<!-- /nav -->
