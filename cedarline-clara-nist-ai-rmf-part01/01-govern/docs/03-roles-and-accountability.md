# AI Roles and Accountability Matrix

<!-- nav -->
[Repository home](../../README.md) › [Part 01: Govern](../README.md) › Document 3 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIG-RACI-001 |
| **Version** | 1.0 |
| **Owner** | Head of AI Governance |
| **Approved by** | AI Governance Committee |
| **Next review** | October 2027 |
| **Full matrix** | `files/CB-AIG-RACI-001_AI_Roles_and_Accountability_Matrix.xlsx` |

## 1. Purpose

This matrix shows who does what across the life of an AI system at Cedarline Bank, so that every AI risk activity has exactly one accountable owner.

## 2. Key

- **R (Responsible):** does the work
- **A (Accountable):** owns the outcome and signs off. Only one A per activity.
- **C (Consulted):** gives input before the work is finished
- **I (Informed):** is told the result

## 3. Roles

| Abbreviation | Role |
| --- | --- |
| **BRC** | Board Risk Committee |
| **AIGC** | AI Governance Committee (chaired by the CRO) |
| **AIGO** | Head of AI Governance and the AI Governance Office |
| **SO** | System owner (for CLARA: Head of Credit Risk Analytics) |
| **DEV** | Model development team (Credit Risk Analytics) |
| **MRM** | Model Risk Management |
| **DPO** | Data Protection Officer |
| **COMP** | Compliance |
| **SEC** | Information Security (CISO) |
| **OPS** | Retail Credit Operations (underwriters and credit officers) |
| **PROC** | Procurement and Third-Party Risk |
| **IA** | Internal Audit |

## 4. Summary matrix

The workbook holds the full matrix of 24 activities. The core activities are:

| Activity | BRC | AIGC | AIGO | SO | DEV | MRM | DPO | COMP | SEC | OPS | PROC | IA |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Set AI risk tolerance | A | R | C | I | | C | C | C | C | | | I |
| Approve AI governance policy | I | A | R | C | | C | C | C | C | | | I |
| Register system and assign tier | | I | A | R | C | | | C | | | | |
| AI impact assessment | | I | C | A | R | C | C | C | C | C | | |
| Data protection impact assessment | | I | C | R | C | | A | C | C | | | |
| Legal and regulatory requirements | | I | C | C | | | C | A | | | | |
| Model development and documentation | | | I | A | R | C | | | C | C | | |
| Test and evaluation | | | C | A | R | C | C | C | R | C | | |
| Independent validation | | I | I | C | C | A | | | C | | | |
| Third-party due diligence | | | C | A | | | C | C | C | | R | |
| Go/no-go decision (Tier 1) | I | A | R | R | C | C | C | C | C | C | | I |
| Human review of referrals and declines | | | | C | | | | C | | A | | |
| Performance and fairness monitoring | | I | C | A | R | C | | C | | C | | |
| AI incident response | I | A | R | R | R | C | C | C | R | C | C | |
| Decommissioning | | A | C | R | R | C | C | C | C | C | C | |
| Independent audit of AI governance | I | I | C | C | | C | | | | | | A |

## 5. Rules

1. Each activity has one **A**. If two roles both claim accountability, the AI Governance Committee decides.
2. The development team cannot validate its own models: **MRM** must be independent of **DEV**.
3. For CLARA, the **system owner** may not approve its own go/no-go decision. That decision belongs to the **AIGC**.
4. The matrix is reviewed every year and after any reorganisation.

## Framework mapping

| This matrix | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Roles and accountability | GOVERN 2.1, 2.3; GOVERN 3.2 | Clause 5.3; A.3.2 | Art. 17(1)(m); 26(2) |
| Independence of validation | GOVERN 4.1 | A.6.2.4 | Art. 17(1)(d) |

<!-- nav -->
---

[← Previous: AI Risk Tolerance Statement](02-ai-risk-tolerance-statement.md) &nbsp;|&nbsp; [Part 01: Govern](../README.md) &nbsp;|&nbsp; [Next: AI System Inventory →](04-ai-system-inventory.md)
<!-- /nav -->
