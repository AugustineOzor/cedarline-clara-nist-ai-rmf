# AI Governance Policy

<!-- nav -->
[Repository home](../../README.md) › [Part 01: Govern](../README.md) › Document 1 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIG-POL-001 |
| **Version** | 1.0 |
| **Owner** | Head of AI Governance |
| **Approved by** | AI Governance Committee, on behalf of the Board Risk Committee |
| **Effective date** | 1 October 2026 |
| **Next review** | October 2027, or earlier after a material regulatory or organisational change |
| **Applies to** | Cedarline Bank Q.P.S.C. and all subsidiaries, including Cedarline Bank Europe DAC |

## 1. Purpose

This policy sets out how Cedarline Bank governs the risks of artificial intelligence (AI). It makes clear who is accountable, which principles every AI system must meet, and the minimum controls required before an AI system can be built, bought or used.

## 2. Scope

This policy applies to every **AI system** that Cedarline develops, buys, configures or uses, including systems embedded in third-party products and generative AI tools used by staff. An AI system is a machine-based system that, for a given set of objectives, produces outputs such as predictions, scores, recommendations, content or decisions that influence real or virtual environments.

It applies to all employees, contractors and third parties acting on Cedarline's behalf.

## 3. Principles

Every AI system at Cedarline must be designed, tested and operated to be:

| Principle | What it means at Cedarline |
| --- | --- |
| **Valid and reliable** | It does what it was approved to do, with measured accuracy that stays within agreed limits over time |
| **Safe** | It does not cause unacceptable harm to customers, staff or the bank, and it fails in a controlled way |
| **Secure and resilient** | It is protected against attack, misuse and data leakage, and can recover from failure |
| **Accountable and transparent** | Every system has a named owner, and its purpose, data and limits are documented |
| **Explainable** | People affected by a decision can be given meaningful reasons for it |
| **Privacy-enhanced** | Personal data is used lawfully, minimally and securely |
| **Fair** | Harmful bias is identified, measured and managed; protected characteristics are never used to disadvantage people |

These principles reflect the trustworthiness characteristics of the NIST AI Risk Management Framework.

## 4. Prohibited uses

Cedarline will not develop or use AI systems that:

- carry out any practice prohibited under Article 5 of the EU AI Act, in any jurisdiction where the bank operates;
- use protected characteristics, or close proxies for them, as inputs to decisions about customers or staff;
- make a final adverse decision about an individual's access to credit, employment or essential services with no meaningful human review;
- process customer or confidential data in public generative AI tools that have not been approved by the AI Governance Office.

## 5. Risk tiers

Every AI system is assigned a risk tier when it is registered. The tier sets the level of control required.

| Tier | Criteria | Examples |
| --- | --- | --- |
| **Tier 1 (high)** | Makes or significantly shapes decisions with legal or similarly significant effects on individuals, or is high-risk under the EU AI Act | Credit decisioning (CLARA), CV screening |
| **Tier 2 (medium)** | Influences customer outcomes or regulatory reporting, with human decision-makers in control | Fraud detection, AML transaction monitoring, customer service chatbot |
| **Tier 3 (low)** | Internal productivity or analytics with no direct effect on individuals | Staff writing assistants, document text extraction |

The Head of AI Governance confirms each tier. Disagreements are escalated to the AI Governance Committee.

## 6. Lifecycle gates

AI systems move through six gates. No system may move to the next gate without the required evidence.

| Gate | Decision | Minimum evidence for Tier 1 | Approver for Tier 1 |
| --- | --- | --- | --- |
| **G0 Intake** | Register the system and assign a tier | Inventory entry; initial use-case description | Head of AI Governance |
| **G1 Design** | Approve the design and data | AI system profile; AI impact assessment; data protection impact assessment; legal and regulatory requirements | AI Governance Committee |
| **G2 Validation** | Confirm the system is fit for purpose | Test and evaluation results; independent model validation; security testing | Model Risk Management |
| **G3 Go-live** | Decide whether to deploy | Go/no-go decision record; risk treatment plan; human oversight procedure; monitoring plan | AI Governance Committee |
| **G4 Review** | Confirm the system still performs as approved | Monitoring reports; annual review; revalidation | System owner, reported to AIGC |
| **G5 Retirement** | Retire the system safely | Decommissioning plan; data disposition record | AI Governance Committee |

Tier 2 systems follow the same gates with lighter evidence and approval by the Head of AI Governance. Tier 3 systems need G0 registration and a short risk check.

## 7. Roles and accountability

- The **Board Risk Committee** sets the bank's AI risk tolerance and oversees AI risk.
- The **AI Governance Committee**, chaired by the Chief Risk Officer, approves this policy, Tier 1 gate decisions and risk acceptances.
- The **Head of AI Governance** runs the AI governance programme, maintains the AI system inventory and monitors compliance with this policy.
- Each AI system has a **system owner** accountable for its risks, documentation and performance throughout its life.
- **Model Risk Management** independently validates models before use and periodically after.
- **Internal Audit** provides independent assurance over the AI governance framework.

Detailed responsibilities are set out in the Roles and Accountability Matrix (CB-AIG-RACI-001).

## 8. Core requirements

1. **Inventory.** Every AI system must be registered in the AI System Inventory before development or purchase begins.
2. **Impact assessment.** Tier 1 and Tier 2 systems must have an AI impact assessment before G1, updated after any material change.
3. **Data governance.** Training and input data must be documented, of known quality and lawfully obtained.
4. **Testing.** Systems must be tested against their requirements, including accuracy, fairness, robustness and security, before deployment.
5. **Human oversight.** Tier 1 systems must have a documented human oversight procedure, including the ability to override, pause or stop the system.
6. **Transparency.** Customers must be told when AI is used in decisions about them and be able to obtain an explanation and human review.
7. **Monitoring.** Deployed systems must be monitored against the thresholds in the AI Risk Tolerance Statement (CB-AIG-RTS-001).
8. **Incidents.** AI incidents must be reported through the AI incident response procedure within the timeframes it sets.
9. **Third parties.** Third-party AI systems, models and data must meet the Third-Party AI and Data Policy (CB-AIG-POL-002).
10. **Records.** Evidence for each gate must be kept for at least the life of the system plus ten years.

## 9. Exceptions

An exception to this policy must be requested in writing by the system owner, with the risk, compensating controls and an expiry date of no more than 12 months. Tier 1 exceptions require AI Governance Committee approval. All exceptions are recorded in the AI risk register.

## 10. Compliance

The AI Governance Office monitors compliance with this policy and reports quarterly to the AI Governance Committee. Breaches may lead to disciplinary action and to suspension of the AI system concerned.

## 11. Related documents

- AI Risk Tolerance Statement (CB-AIG-RTS-001)
- AI Roles and Accountability Matrix (CB-AIG-RACI-001)
- AI System Inventory (CB-AIG-INV-001)
- Legal and Regulatory Obligations Register (CB-AIG-REG-001)
- Third-Party AI and Data Policy (CB-AIG-POL-002)
- AI Risk Training Plan (CB-AIG-TRN-001)

## Framework mapping

| This policy | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Principles (s.3) | GOVERN 1.2 | Clause 5.2; A.2.2 | Art. 9, 10, 13, 14, 15 |
| Risk tiers and gates (s.5, s.6) | GOVERN 1.3, 1.4 | Clause 6.1; A.6.2 | Art. 9, 16, 17 |
| Roles (s.7) | GOVERN 2.1, 2.3 | Clause 5.3; A.3.2 | Art. 17(1)(m), 26 |
| Inventory (s.8.1) | GOVERN 1.6 | A.4.2 to A.4.5 | Art. 49 |
| Monitoring and review (s.8.7) | GOVERN 1.5 | Clause 9.1 | Art. 72 |
| Third parties (s.8.9) | GOVERN 6.1 | A.10 | Art. 25 |

<!-- nav -->
---

[← Previous: Part 01 overview](../README.md) &nbsp;|&nbsp; [Part 01: Govern](../README.md) &nbsp;|&nbsp; [Next: AI Risk Tolerance Statement →](02-ai-risk-tolerance-statement.md)
<!-- /nav -->
