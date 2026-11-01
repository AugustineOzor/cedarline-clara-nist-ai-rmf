# Human Oversight, Override and Stop Procedure: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 2 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-HOP-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Retail Credit Operations |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Applies to** | Underwriters, credit officers, Credit Quality Assurance, Credit Risk Analytics on-call staff |

## 1. Purpose

CLARA recommends; people decide. This procedure sets who oversees CLARA, how they review its recommendations, how they override them, and how CLARA's automatic decisions can be paused or switched off when it is not working as intended.

## 2. Oversight roles

| Role | Oversight responsibility |
| --- | --- |
| **Underwriter** | Reviews referred applications and makes the final decision |
| **Credit officer** | Reviews every recommended decline; may approve, refer or decline |
| **Credit Quality Assurance** | Samples decisions monthly to check that reviews are genuine |
| **CLARA duty manager** (Credit Risk Analytics, on rota) | Watches daily operational alerts; can pause automatic approvals |
| **Head of Retail Credit Operations** | Accountable for review quality and override behaviour |
| **Chief Risk Officer** | Can order CLARA switched off entirely |

Only staff who have passed the "Working with CLARA" training may review CLARA cases (CB-AIG-TRN-001).

## 3. Reviewing a case

For every referred case and recommended decline, the reviewer must:

1. Read the application data and documents **before** looking at CLARA's recommendation. For recommended declines, the screen hides the recommendation until the reviewer confirms this step.
2. Review CLARA's probability of default, grade and four reason codes.
3. Check data-quality warnings, for example missing bureau data or low-confidence document extraction.
4. Consider information CLARA does not see, such as a recent salary increase confirmed by the employer, or a one-off missed payment with a documented reason.
5. Decide, and record a reason. **A reason is required whether the reviewer agrees or disagrees with CLARA.**

## 4. Overriding CLARA

Reviewers may override any recommendation. Overrides are expected and are not penalised.

| Override | Example reasons | Extra approval |
| --- | --- | --- |
| Approve a recommended decline | Verified new income; bureau error confirmed; thin file with strong alternative data | Credit officer's own authority up to QAR 50,000 / EUR 12,500; above that, a senior credit officer |
| Decline a recommended approval or referral | Information indicating fraud, affordability concerns not visible to CLARA | Reviewer's own authority |
| Change amount or limit | Affordability supports a different amount | Reviewer's own authority within mandate |

Every override records the reviewer, reason code, free-text explanation and supporting evidence. Override patterns feed monthly monitoring and model improvement.

## 5. Customer requests for human review

Any applicant can ask for a person to review a decision involving CLARA, provide extra information, and contest the outcome.

- Requests are logged by Customer Service and passed to a credit officer who did **not** make the original decision.
- The review is completed within **5 working days**, and the customer receives the outcome and main reasons in writing.
- Requests and outcomes are reported monthly as part of complaints and fairness monitoring.

## 6. Pausing and stopping CLARA

| Level | What happens | Who can trigger | When | Target time |
| --- | --- | --- | --- | --- |
| **1. Pause automatic approvals** | All applications are routed to manual review; CLARA still scores and gives reasons | CLARA duty manager; Head of Retail Credit Operations | Amber or red alert under investigation; data-quality issue; supplier problem | 15 minutes |
| **2. Fall back to Scorecard 19** | CLARA stops scoring; Scorecard 19 and manual review take over | Head of Credit Risk Analytics; Chief Risk Officer | Red limit reached; suspected model failure; Severity 1 incident | 30 minutes |
| **3. Full suspension** | No AI-supported credit decisions until the AI Governance Committee approves a restart | Chief Risk Officer | Serious incident; regulator instruction; suspected unlawful discrimination | Immediate |

Restarting after levels 2 or 3 requires a root-cause analysis, evidence the issue is fixed, and approval by the AI Governance Committee (level 3) or the Head of Credit Risk Analytics with Model Risk Management (level 2).

## 7. Monitoring the oversight itself

| Measure | Green | Action if outside green |
| --- | --- | --- |
| Override rate (all reviewers) | 3% to 15% | Investigate; below 3% suggests automation bias, above 15% suggests model or data issues |
| Override rate by reviewer | Within 10 points of team average | One-to-one review and refresher training |
| Agreed declines without a meaningful reason | 0 in quality sample | Coaching; repeated findings lead to access removal |
| Human review requests completed within 5 days | At least 95% | Escalate to Head of Retail Credit Operations |

## Framework mapping

| This procedure | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act and other |
| --- | --- | --- | --- |
| Human oversight roles and competence | GOVERN 3.2; MANAGE 2.4 | A.9.2; A.9.3 | AI Act Art. 14; 26(2) |
| Override and stop functions | MANAGE 2.4; MANAGE 2.3 | A.9.2 | AI Act Art. 14(4)(d), (e) |
| Right to human review | GOVERN 5.1; MANAGE 4.3 | A.8.3 | GDPR Art. 22(3); CCD Art. 18 |

<!-- nav -->
---

[← Previous: AI Risk Treatment Plan: CLARA](01-risk-treatment-plan.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: Go/No-Go Decision Record: CLARA →](03-go-no-go-decision-record.md)
<!-- /nav -->
