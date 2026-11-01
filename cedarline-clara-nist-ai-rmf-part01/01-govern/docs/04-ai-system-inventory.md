# AI System Inventory

<!-- nav -->
[Repository home](../../README.md) › [Part 01: Govern](../README.md) › Document 4 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIG-INV-001 |
| **Version** | 1.0 (snapshot at 1 October 2026) |
| **Owner** | Head of AI Governance |
| **Update frequency** | Continuously; formally reviewed every quarter |
| **Full register** | `files/CB-AIG-INV-001_AI_System_Inventory.xlsx` |

## 1. Purpose

The inventory is the single, authoritative list of every AI system Cedarline Bank builds, buys or uses. Each entry records what the system does, who owns it, who it affects, how risky it is and where it is in its lifecycle. No AI system may be developed, bought or used before it is registered here (AI Governance Policy, section 8.1).

## 2. What each entry records

Identity and ownership, purpose and users, affected people, build type (in-house or third party), model type, data categories, jurisdictions, lifecycle stage, internal risk tier, EU AI Act classification, Cedarline's role under the Act, status of key assessments, review dates and risk priority. The workbook holds the full set of 24 fields.

## 3. Current inventory

| ID | System | Purpose | Build | Stage | Tier | EU AI Act classification | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **AI-CR-001** | **CLARA** | Probability of default and decision recommendation for unsecured lending | In-house | Validation and pilot | 1 | High-risk: Annex III 5(b) (provider and deployer) | **Critical** |
| AI-CR-002 | Collections Prioritiser | Ranks overdue accounts for collector contact | In-house | Production | 2 | Not high-risk (assessed) | High |
| AI-FR-001 | Card Fraud Detection | Scores card transactions for fraud in real time | Third party | Production | 2 | Not high-risk: fraud detection is excluded from Annex III 5(b) | High |
| AI-FC-001 | AML Transaction Monitoring | Flags unusual transactions for investigators | Third party | Production | 2 | Not high-risk (assessed) | High |
| AI-CS-001 | Ask Cedar | Customer service chatbot on a third-party large language model | Third party, configured in-house | Production | 2 | Limited risk: transparency duties (Art. 50) | High |
| AI-HR-001 | Talent Screen | Ranks job applicants' CVs | Third party | **On hold** | 1 | High-risk: Annex III 4(a) (deployer) | High |
| AI-PR-001 | Staff Copilot | Writing and summarising assistant for staff | Third party | Production | 3 | Minimal risk | Medium |
| AI-OP-001 | DocRead | Extracts data from customer identity and income documents | Third party | Production | 3 | Minimal risk | Medium |
| AI-MK-001 | Next Best Offer | Predicts which product a customer may want | In-house | Production | 3 | Minimal risk | Low |

## 4. Key observations

1. **Two Tier 1 systems.** CLARA is the bank's most significant AI system. Talent Screen is on hold until a full deployer assessment is completed, because CV screening is high-risk under Annex III 4(a).
2. **Most systems involve third parties.** Six of nine involve an external supplier, which makes the Third-Party AI and Data Policy central to the programme.
3. **Classification is recorded with its reasoning.** For example, Card Fraud Detection is not high-risk because fraud detection is expressly excluded from the credit-scoring category, and the reason is noted in the register.
4. **Assessment gaps tracked.** The Collections Prioritiser still needs an updated AI impact assessment (due December 2026) and is flagged amber.

## 5. Maintaining the inventory

- **New systems** are added at gate G0, before any development or purchase.
- **Changes** to purpose, data, model or supplier must be recorded within 10 working days.
- **Quarterly review:** the AI Governance Office confirms each entry with its owner and searches for unregistered "shadow AI" through procurement records, network logs and staff surveys.
- **Retired systems** stay in the register, marked as retired, for ten years.

## Framework mapping

| This inventory | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Inventory and classification | GOVERN 1.6; MAP 1.1 | A.4.2 to A.4.5; Clause 4.3 | Art. 6; 49 |

<!-- nav -->
---

[← Previous: AI Roles and Accountability Matrix](03-roles-and-accountability.md) &nbsp;|&nbsp; [Part 01: Govern](../README.md) &nbsp;|&nbsp; [Next: Legal and Regulatory Obligations Register: CLARA →](05-legal-and-regulatory-obligations-register.md)
<!-- /nav -->
