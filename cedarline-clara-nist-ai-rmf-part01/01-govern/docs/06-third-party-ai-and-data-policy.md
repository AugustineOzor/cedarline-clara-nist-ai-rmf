# Third-Party AI and Data Policy

<!-- nav -->
[Repository home](../../README.md) › [Part 01: Govern](../README.md) › Document 6 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIG-POL-002 |
| **Version** | 1.0 |
| **Owner** | Head of Procurement and Third-Party Risk |
| **Approved by** | AI Governance Committee |
| **Effective date** | 1 October 2026 |
| **Next review** | October 2027 |

## 1. Purpose

Most AI risk at Cedarline Bank enters through third parties: purchased AI systems, external models, data providers, cloud platforms and open-source components. This policy sets the minimum controls for selecting, contracting, monitoring and exiting those relationships.

## 2. Scope

This policy covers any third party that supplies:

- an AI system or AI-enabled product;
- a model, including pre-trained and general-purpose AI models;
- data used to train, test or run an AI system, including bureau and verification data;
- platforms or tools used to build, host or monitor AI systems;
- open-source AI libraries and models used in production.

## 3. Requirements before contract

| Requirement | Tier 1 | Tier 2 | Tier 3 |
| --- | --- | --- | --- |
| Register the system or component in the AI System Inventory | Yes | Yes | Yes |
| AI due diligence questionnaire covering purpose, training data, testing, bias, security, incidents and sub-processors | Full | Full | Short |
| Evidence of testing for accuracy, bias and robustness relevant to our use | Required | Required | On request |
| Security assessment, including data location and access | Required | Required | Required |
| Data protection review, and data processing agreement where personal data is involved | Required | Required | Required |
| Confirmation of the supplier's role and obligations under the EU AI Act | Required | Where relevant | Not required |
| Concentration and exit assessment | Required | Required | Not required |
| Approval | AI Governance Committee | Head of AI Governance | Procurement |

## 4. Minimum contract terms

Contracts for Tier 1 and Tier 2 AI suppliers must include:

1. **Permitted use:** our data may be used only to provide the service, and never to train the supplier's models without our written consent.
2. **Transparency:** the supplier provides documentation on how the system works, its intended purpose, known limits and performance.
3. **Change notice:** at least 30 days' notice of material changes to models, data sources or sub-processors, and immediate notice of emergency changes.
4. **Incident notice:** notification of security or AI incidents affecting our service within 24 hours.
5. **Audit and information rights:** for Cedarline, its auditors and its regulators.
6. **Regulatory cooperation:** support for our obligations under the EU AI Act, GDPR, DORA and Qatar requirements.
7. **Service levels:** availability and performance targets, with remedies.
8. **Exit:** return or deletion of our data, transition support and a reasonable notice period.

## 5. Open-source components

Open-source AI libraries and models may be used when they come from a reputable source, their licence permits commercial use, they are pinned to a reviewed version, and they are scanned for known vulnerabilities. CLARA's open-source components (XGBoost, SHAP, scikit-learn) are listed in its third-party component register.

## 6. Ongoing monitoring

- Tier 1 suppliers are reviewed **every six months** and Tier 2 suppliers **every year**: performance, incidents, changes and audit results.
- Significant drops in data quality or service from a supplier are logged as AI incidents.
- Each Tier 1 dependency must have a tested **contingency plan**. For CLARA, if the Verilytix verification service fails, applications are routed to manual income verification and auto-approval is suspended for affected applications.

## 7. Exit

Before a contract ends, the system owner confirms that data has been returned or deleted, that access has been revoked and that the replacement or fallback is working.

## Framework mapping

| This policy | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act and other |
| --- | --- | --- | --- |
| Third-party risk policies | GOVERN 6.1 | A.10.2, A.10.3 | AI Act Art. 25; DORA Art. 28 to 30 |
| Contingency for supplier failure | GOVERN 6.2 | A.10.3 | DORA Art. 28(8) |
| Third-party components mapped | MAP 4.1, 4.2 | A.10.3 | AI Act Art. 25(4) |

<!-- nav -->
---

[← Previous: Legal and Regulatory Obligations Register: CLARA](05-legal-and-regulatory-obligations-register.md) &nbsp;|&nbsp; [Part 01: Govern](../README.md) &nbsp;|&nbsp; [Next: AI Risk Training Plan →](07-ai-risk-training-plan.md)
<!-- /nav -->
