# Part 02: Map

<!-- nav -->
[Repository home](../README.md) › Part 02: Map
<!-- /nav -->

**NIST AI RMF function: MAP.** This part establishes the context for CLARA: what it is for and what it is not for, who it affects, what could go wrong for whom, what it must achieve to be trustworthy, and which outside components it depends on. Everything here feeds the testing in Part 03.

## Documents

| # | Document | ID | What it does | Files |
| --- | --- | --- | --- | --- |
| 1 | [AI System Profile](docs/01-ai-system-profile.md) | CB-AIM-PRF-001 | Intended purpose and out-of-scope uses, decision flow and routing rules, users, model and data, expected benefits, known limits | Word |
| 2 | [AI Impact Assessment](docs/02-ai-impact-assessment.md) | CB-AIM-AIA-001 | 11 potential harms rated before and after mitigation, fundamental rights, the non-AI alternative, and conditions for proceeding | Word |
| 3 | [Trustworthiness Requirements Specification](docs/03-trustworthiness-requirements.md) | CB-AIM-REQ-001 | 31 testable requirements across eight trustworthiness characteristics, each with an acceptance criterion and verification method | Word, Excel |
| 4 | [Third-Party Component Register](docs/04-third-party-component-register.md) | CB-AIM-TPC-001 | Nine external data sources, services, platforms and libraries with criticality, risks, controls and contingency | Word, Excel |
| 5 | [Initial Risk Identification](docs/05-initial-risk-identification.md) | CB-AIM-RSK-001 | 18 risks found during mapping, linked to their sources, ready for scoring in Part 03 | Word |

## Highlights

- **Clear scope.** CLARA is limited to unsecured lending decisions; pricing, limit cuts and collections are explicitly out of scope.
- **Groups at risk named.** Applicants new to credit, expatriates, women and the self-employed are assessed specifically, not just "applicants".
- **Requirements you can test.** Every requirement has a pass/fail criterion, such as an adverse impact ratio of at least 0.80 or reason-code fidelity of at least 98%.
- **Traceability.** Harms (IA-xx) link to requirements (REQ-xx), components (TPC-xx) and risks (R-xx), so nothing is lost between parts.
- **Working spreadsheets.** The traceability matrix counts passes, failures and go-live blockers automatically once Part 03 records results.

## NIST AI RMF coverage

| Subcategory | Covered by |
| --- | --- |
| MAP 1.1, 1.6 Context, intended purpose and requirements | System profile; requirements specification |
| MAP 2.1 to 2.3 Tasks, methods, limits and data | System profile, sections 5 and 7 |
| MAP 3.1 to 3.4 Benefits, costs and human roles | System profile; impact assessment |
| MAP 4.1, 4.2 Third-party components and their risks | Third-party component register |
| MAP 5.1, 5.2 Impacts and stakeholder engagement | Impact assessment |

<!-- nav -->
---

[← Previous: AI Risk Training Plan](../01-govern/docs/07-ai-risk-training-plan.md) &nbsp;|&nbsp; [Repository home](../README.md) &nbsp;|&nbsp; [Next: AI System Profile: CLARA →](docs/01-ai-system-profile.md)
<!-- /nav -->
