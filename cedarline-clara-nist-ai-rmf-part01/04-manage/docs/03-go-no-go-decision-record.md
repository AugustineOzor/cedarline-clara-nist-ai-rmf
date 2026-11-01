# Go/No-Go Decision Record: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 3 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-GNG-001 |
| **System** | AI-CR-001 CLARA, model version 1.2 |
| **Gate** | G3 Go-live (AI Governance Policy, section 6) |
| **Decision body** | AI Governance Committee |
| **Meeting date** | 26 November 2026 |
| **Chair** | Chief Risk Officer |
| **Record prepared by** | AI Governance Office |

## 1. Decision requested

The system owner asked the committee to approve CLARA for live use in Qatar and the EU.

## 2. Decision

| Scope | Decision |
| --- | --- |
| **Qatar: limited live pilot** | **GO, with conditions**, from 18 January 2027 for 12 weeks |
| **Qatar: full launch** | **Not yet decided.** Return to the committee after the pilot, expected June 2027 |
| **EU (Ireland)** | **NO-GO** until the conformity assessment is complete. Expected decision October 2027, before 2 December 2027 |

## 3. Limited pilot terms (Qatar)

| Term | Pilot setting | Full design (for comparison) |
| --- | --- | --- |
| Share of Qatar applications | 25%, allocated at random | 100% |
| Automatic approval | Grades A and B only, up to QAR 20,000 | Grades A to C, up to QAR 50,000 |
| Other grades | Referred to underwriters | As in the system profile |
| Recommended declines | Reviewed by a credit officer | Same |
| Override reporting | Weekly | Monthly after three months |
| Fallback | Scorecard 19 remains live for the other 75% | Fallback only |

## 4. Evidence considered

| Evidence | Document | Committee view |
| --- | --- | --- |
| System profile and intended purpose | CB-AIM-PRF-001 | Scope clear and appropriate |
| AI impact assessment | CB-AIM-AIA-001 | Conditions 1 and 3 met; conditions 2 (FRIA, DPIA) not yet met for the EU |
| Test results and validation opinion | CB-AIMS-TER-001 | Fit for purpose, with conditions |
| Requirements traceability | CB-AIM-REQ-001 v1.1 | 28 of 31 met; 3 open, all EU-related documentation |
| AI risk register | CB-AIMS-RR-001 | No Critical or High residual risks; 5 Medium with treatment plan |
| Risk treatment plan | CB-AIMG-RTP-001 | Approved at this meeting |
| Human oversight procedure | CB-AIMG-HOP-001 | Approved at this meeting |
| Monitoring plan | CB-AIMG-MON-001 | Approved at this meeting |
| Qatar privacy assessment under PDPPL | CB-DPO-PIA-014 | Complete |

## 5. Alternatives considered

| Option | Committee view |
| --- | --- |
| Full launch in Qatar now | Rejected: reviewer behaviour and live performance not yet observed |
| **Limited live pilot in Qatar** | **Chosen:** produces real evidence on override behaviour and early arrears with limited exposure |
| Stay on Scorecard 19 (non-AI alternative) | Rejected: lower accuracy (Gini 0.47), slower decisions, generic reasons and no fairness testing |
| Delay all use until EU readiness | Rejected: no Qatar-specific reason to wait, and the pilot reduces EU launch risk |

## 6. Conditions

1. Weekly override-rate reporting and monthly quality reviews during the pilot (R-07).
2. Monthly intersectional fairness report; if any group's adverse impact ratio falls below 0.80, automatic approvals are paused for review (R-03).
3. Early-warning arrears indicators reported monthly from week 8 (R-01).
4. All three open EU documentation items closed before the EU decision (R-16).
5. Any red limit reported to the Chair within 2 working days.

## 7. Views recorded

| Member | View |
| --- | --- |
| Chief Risk Officer (Chair) | Support with conditions |
| Head of AI Governance | Support with conditions |
| Head of Compliance | Support for Qatar pilot; EU no-go until FRIA complete |
| Data Protection Officer | Support for Qatar pilot; EU no-go until DPIA approved |
| Head of Model Risk Management | Support; revalidation after 12 months |
| CISO | Support; no open high findings |
| Head of Retail Lending (business) | Support; would prefer a larger pilot share |
| Head of Retail Credit Operations | Support; reviewer training complete for pilot team |
| Head of Internal Audit (observer, non-voting) | No objection; will audit the pilot in Q2 2027 |

**Result:** approved unanimously by voting members, with the conditions above. The system owner did not vote (AI Governance Policy, RACI rule 3).

## 8. Follow-up

| Item | Owner | Date |
| --- | --- | --- |
| Pilot start | Head of Retail Credit Operations | 18 January 2027 |
| Pilot interim report | Head of Credit Risk Analytics | 15 March 2027 |
| Full Qatar launch decision | AI Governance Committee | June 2027 |
| EU decision | AI Governance Committee | October 2027 |

## Framework mapping

| This record | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Documented decision on whether to deploy | MANAGE 1.1 | A.6.2.5 | Art. 9(5); 43 |
| Benefits and alternatives considered | MANAGE 1.1; MAP 3.2 | Clause 6.1.4 | Annex IV(2) |
| Accountable approval | GOVERN 2.3 | Clause 5.1 | Art. 17(1)(m) |

<!-- nav -->
---

[← Previous: Human Oversight, Override and Stop Procedure: CLARA](02-human-oversight-procedure.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: AI Incident Response Procedure →](04-ai-incident-response-procedure.md)
<!-- /nav -->
