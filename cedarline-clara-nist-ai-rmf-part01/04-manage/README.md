# Part 04: Manage

<!-- nav -->
[Repository home](../README.md) › Part 04: Manage
<!-- /nav -->

**NIST AI RMF function: MANAGE.** This part acts on what Parts 01 to 03 found: it treats the remaining risks, sets how people oversee and can stop CLARA, records the go-live decision, and covers what happens when things go wrong, how CLARA is monitored in production, how supplier failures are handled and how the system is eventually retired.

## Documents

| # | Document | ID | What it does | Files |
| --- | --- | --- | --- | --- |
| 1 | [AI Risk Treatment Plan](docs/01-risk-treatment-plan.md) | CB-AIMG-RTP-001 | 19 actions for the five Medium residual risks, with owners, deadlines and success measures | Word, Excel |
| 2 | [Human Oversight, Override and Stop Procedure](docs/02-human-oversight-procedure.md) | CB-AIMG-HOP-001 | How reviewers assess and override CLARA, customer requests for human review, and three levels of pause, fallback and suspension | Word |
| 3 | [Go/No-Go Decision Record](docs/03-go-no-go-decision-record.md) | CB-AIMG-GNG-001 | The G3 decision: a limited live pilot in Qatar, no-go for the EU until conformity, with evidence, alternatives, conditions and recorded views | Word |
| 4 | [AI Incident Response Procedure](docs/04-ai-incident-response-procedure.md) | CB-AIMG-IRP-001 | Severity levels, nine response steps and regulatory notifications under the EU AI Act, GDPR, DORA and Qatar requirements | Word |
| 5 | [Post-Deployment Monitoring and Continuous Improvement Plan](docs/05-post-deployment-monitoring-plan.md) | CB-AIMG-MON-001 | 15 metrics with green, amber and red limits, feedback loops, change and retraining triggers, and reporting | Word, Excel |
| 6 | [Third-Party AI Contingency Plan](docs/06-third-party-contingency-plan.md) | CB-AIMG-TCP-001 | Eight supplier failure scenarios with detection, actions, recovery targets and tests | Word |
| 7 | [AI System Decommissioning Procedure](docs/07-ai-system-decommissioning-procedure.md) | CB-AIMG-DEC-001 | Ten retirement steps, data disposition and sign-off | Word |

## Highlights

- **A realistic decision, not a rubber stamp.** The committee approved a limited live pilot in Qatar (25% of applications, tighter auto-approval limits) and said no to the EU until the conformity assessment is complete.
- **Oversight designed against automation bias.** Reviewers see the application before CLARA's recommendation, must give a reason even when they agree, and are monitored for override rates that are too low as well as too high.
- **Stop functions with clear owners and times.** Pause automatic approvals in 15 minutes, fall back to Scorecard 19 in 30 minutes, or suspend entirely.
- **Lessons carried forward.** Monitoring adds the intersectional fairness checks and early-warning arrears indicators that Part 03 showed were needed.
- **Working spreadsheets.** The monitoring scorecard sets Green, Amber or Red automatically from each value; the treatment tracker flags overdue actions against a report date.

## NIST AI RMF coverage

| Subcategory | Covered by |
| --- | --- |
| MANAGE 1.1 to 1.4 Deployment decision, prioritised responses, residual risk | Go/no-go record; risk treatment plan |
| MANAGE 2.1 to 2.4 Resources, sustaining value, responding to unknown risks, disengaging the system | Treatment plan; incident response; oversight procedure |
| MANAGE 3.1, 3.2 Third-party risks and monitoring | Contingency plan; monitoring plan (M-15) |
| MANAGE 4.1 to 4.3 Post-deployment monitoring, improvement, incident communication | Monitoring plan; incident response |
| GOVERN 1.7 Decommissioning | Decommissioning procedure |

<!-- nav -->
---

[← Previous: Measurement Effectiveness Review: CLARA](../03-measure/docs/04-measurement-effectiveness-review.md) &nbsp;|&nbsp; [Repository home](../README.md) &nbsp;|&nbsp; [Next: AI Risk Treatment Plan: CLARA →](docs/01-risk-treatment-plan.md)
<!-- /nav -->
