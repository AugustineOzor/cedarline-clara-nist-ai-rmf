# AI System Decommissioning Procedure

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 7 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-DEC-001 |
| **Scope** | All AI systems in the AI System Inventory; CLARA used as the worked example |
| **Version** | 1.0 |
| **Owner** | Head of AI Governance |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Gate** | G5 Retirement (AI Governance Policy, section 6) |

## 1. Purpose

AI systems must be retired as carefully as they are launched. This procedure makes sure that when an AI system is withdrawn, decisions keep flowing, data and records are handled lawfully, dependent processes are not left broken, and nothing is left running unnoticed.

## 2. Triggers

- Replacement by a new system or model version
- Persistent red limits that cannot be fixed
- Change in law or regulator instruction
- End of business need or product withdrawal
- Loss of a critical supplier with no viable alternative

## 3. Steps

| Step | Actions | Owner | CLARA example |
| --- | --- | --- | --- |
| **1. Decision** | Retirement proposal with reasons, impact and timing; AIGC approval for Tier 1 | System owner | Replacing CLARA v1 with a successor, or returning to a non-AI process |
| **2. Impact on dependent processes** | List every process, report and system that uses the AI system's outputs | System owner | Credit decision engine, collections strategy, regulatory capital reporting, monitoring dashboards |
| **3. Replacement or fallback ready** | Successor validated and approved, or manual process staffed | System owner; Operations | Successor through G2 and G3, or Scorecard 19 plus manual underwriting |
| **4. Communication** | Inform users, affected teams, suppliers, and customers where relevant | System owner; Communications | Underwriters retrained; customer notices updated if the decision process changes |
| **5. Switch-off** | Stop new decisions; remove integrations; revoke access and service accounts | Credit Risk Analytics; CISO | Scoring endpoint removed; API keys revoked |
| **6. Data disposition** | Apply the retention schedule to each data set | DPO; system owner | See section 4 |
| **7. Model and documentation archive** | Archive final model, code, documentation, validation and monitoring records | Model Risk Management | Kept read-only for 10 years |
| **8. Supplier exit** | Return or deletion of data by suppliers; confirm in writing | Procurement | Verilytix deletion certificate |
| **9. Regulatory steps** | Update records with regulators where needed | Head of AI Governance; Compliance | Update or withdraw the EU database registration; inform the regulator if required |
| **10. Close-out** | Mark the system "Retired" in the inventory; post-retirement review after 3 months | Head of AI Governance | Confirm no traffic, no access, no residual costs |

## 4. Data disposition

| Data | Action | Retention |
| --- | --- | --- |
| Decision logs (inputs, outputs, reasons, reviewer decisions) | Keep, read-only | At least 10 years after the last decision, to support complaints, audits and regulators |
| Training, validation and test data | Delete, or keep only if legally required and approved by the DPO | Per retention schedule |
| Protected-attribute data used for fairness testing | Delete | No longer than needed for final fairness reporting |
| Model artefacts and code | Archive, read-only | 10 years |
| Supplier-held data | Return or delete under contract | Deletion confirmed in writing |

## 5. Sign-off

| Role | Confirms |
| --- | --- |
| System owner | Dependent processes migrated; switch-off complete |
| CISO | Access revoked; infrastructure removed |
| DPO | Data disposition complete |
| Model Risk Management | Archive complete |
| Head of AI Governance | Inventory updated; regulatory steps done |

## Framework mapping

| This procedure | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Safe decommissioning | GOVERN 1.7; MANAGE 2.4 | A.6.2.7 | Art. 12; 18; 49 |
| Record keeping after retirement | GOVERN 1.7 | A.6.2.7 | Art. 18; 19 |

<!-- nav -->
---

[← Previous: Third-Party AI Contingency Plan: CLARA](06-third-party-contingency-plan.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Finish: back to repository home →](../../README.md)
<!-- /nav -->
