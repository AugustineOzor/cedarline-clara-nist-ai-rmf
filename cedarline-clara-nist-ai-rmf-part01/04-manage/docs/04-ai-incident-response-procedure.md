# AI Incident Response Procedure

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 4 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-IRP-001 |
| **Scope** | All Tier 1 and Tier 2 AI systems; CLARA examples used throughout |
| **Version** | 1.0 |
| **Owner** | Head of AI Governance, with the CISO |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Related** | Bank Incident Management Policy; Personal Data Breach Procedure; ICT Incident Reporting Procedure (DORA) |

## 1. Purpose

AI systems can fail in ways ordinary IT incident processes do not catch: a model can stay "up" while making unfair or wrong decisions. This procedure sets how AI incidents are detected, triaged, contained, fixed, reported and learned from.

## 2. What counts as an AI incident

An event where an AI system behaves, or may have behaved, in a way that causes or could cause harm, breaches a requirement, or falls outside its approved limits. For example:

- a red limit in the monitoring plan is reached;
- a group of customers is treated unfairly;
- wrong reasons are given for decisions;
- a supplier's data or service fails or changes and affects decisions;
- the model, data or pipeline is tampered with or compromised;
- the system is used outside its intended purpose.

## 3. Severity levels

| Severity | Description | CLARA examples | Response |
| --- | --- | --- | --- |
| **S1 Critical** | Actual or likely serious harm to many customers, possible breach of law, or serious incident under the EU AI Act | Evidence of unlawful discrimination; decisions driven by corrupted data at scale; compromised model | Stop level 2 or 3 within 30 minutes; CRO informed within 1 hour |
| **S2 High** | Harm to some customers, or a red limit reached | AIR below 0.80; calibration beyond ±20%; logs missing for a day | Pause automatic approvals within 15 minutes; system owner informed within 2 hours |
| **S3 Medium** | Amber limit reached, or limited impact | PSI 0.15; override rate 18%; supplier outage handled by fallback | Investigate within 10 working days |
| **S4 Low** | No customer impact | Single reason-code template error caught before sending | Fix in normal change process |

When in doubt, classify higher and downgrade later.

## 4. Response steps

| Step | Actions | Lead |
| --- | --- | --- |
| **1. Detect and report** | Alerts from monitoring, override patterns, complaints, staff reports, supplier notices, audit findings. Anyone can report through the AI incident form or the service desk. | Anyone |
| **2. Triage** | Confirm the facts, set severity, open an incident record, assemble the response team | CLARA duty manager |
| **3. Contain** | Pause, fall back or suspend (Human Oversight Procedure, section 6); preserve logs and evidence | Head of Credit Risk Analytics |
| **4. Assess impact** | Identify affected applications and customers, and whether any were wrongly declined or approved | Credit Risk Analytics; Compliance |
| **5. Notify** | Internal escalation and any regulatory notifications (section 5) | Head of Compliance; DPO; CISO |
| **6. Fix** | Root-cause analysis; fix data, model, configuration or supplier issue; validate the fix | System owner; MRM |
| **7. Remediate customers** | Re-review affected decisions; contact customers; offer corrections or redress | Head of Retail Credit Operations |
| **8. Restart** | Restart approval as required by the Human Oversight Procedure | AIGC or system owner with MRM |
| **9. Learn** | Post-incident review within 20 working days; update risk register, tests, monitoring and training | Head of AI Governance |

## 5. Regulatory notifications

Timelines below are summaries. Compliance and Legal confirm what applies in each case.

| Regime | Applies when | Timeline (summary) | Owner |
| --- | --- | --- | --- |
| **EU AI Act, Art. 73** (from 2 December 2027 for CLARA in the EU) | A serious incident involving a high-risk AI system, including an infringement of EU law protecting fundamental rights | Report to the market surveillance authority as soon as a causal link is established or reasonably likely, and within 15 days of becoming aware; shorter limits for the most severe cases | Head of AI Governance |
| **GDPR, Art. 33 and 34** | A personal data breach | Data Protection Commission within 72 hours where required; affected people without undue delay if high risk | DPO |
| **DORA** | A major ICT-related incident affecting the EU subsidiary | Initial, intermediate and final reports within DORA's timelines | CISO |
| **Qatar** | Incidents meeting Qatar Central Bank or PDPPL notification criteria | As set by the applicable requirements | Head of Compliance; DPO |

## 6. Records

Every incident record holds the timeline, severity, decisions, affected customers, notifications made, root cause, fixes and lessons learned. Records are kept for at least ten years and reported in summary to the AI Governance Committee monthly.

## 7. Testing this procedure

A tabletop exercise is held every year, using a realistic CLARA scenario (for example, a supplier silently changing its income-verification method). Findings update this procedure.

## Framework mapping

| This procedure | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act and other |
| --- | --- | --- | --- |
| Incident detection, response and recovery | MANAGE 2.3; MANAGE 4.3 | A.8.4 | AI Act Art. 73 |
| Communication to affected parties | MANAGE 4.3; GOVERN 4.3 | A.8.4; A.8.5 | GDPR Art. 34 |
| Third-party incidents | MANAGE 3.1 | A.10.3 | DORA Art. 19 |

<!-- nav -->
---

[← Previous: Go/No-Go Decision Record: CLARA](03-go-no-go-decision-record.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: Post-Deployment Monitoring and Continuous Improvement Plan: CLARA →](05-post-deployment-monitoring-plan.md)
<!-- /nav -->
