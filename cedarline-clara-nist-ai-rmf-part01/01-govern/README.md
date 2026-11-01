# Part 01: Govern

<!-- nav -->
[Repository home](../README.md) › Part 01: Govern
<!-- /nav -->

**NIST AI RMF function: GOVERN.** This part sets up the structures that every later decision about CLARA depends on: the policy, how much risk the bank will accept, who is accountable, which AI systems exist, which laws apply, how suppliers are controlled and how people are trained.

## Documents

| # | Document | ID | What it does | Files |
| --- | --- | --- | --- | --- |
| 1 | [AI Governance Policy](docs/01-ai-governance-policy.md) | CB-AIG-POL-001 | Principles, prohibited uses, risk tiers, six lifecycle gates and core requirements | Word |
| 2 | [AI Risk Tolerance Statement](docs/02-ai-risk-tolerance-statement.md) | CB-AIG-RTS-001 | Board-approved appetite by risk category, with green, amber and red limits for Tier 1 credit models | Word |
| 3 | [AI Roles and Accountability Matrix](docs/03-roles-and-accountability.md) | CB-AIG-RACI-001 | RACI for 24 AI risk activities across 12 roles, with an automatic one-accountable-owner check | Word, Excel |
| 4 | [AI System Inventory](docs/04-ai-system-inventory.md) | CB-AIG-INV-001 | Nine AI systems with tier, EU AI Act classification, owners and assessment status | Word, Excel |
| 5 | [Legal and Regulatory Obligations Register](docs/05-legal-and-regulatory-obligations-register.md) | CB-AIG-REG-001 | 24 obligations for CLARA across the EU AI Act, GDPR, consumer credit, DORA and Qatar law | Word, Excel |
| 6 | [Third-Party AI and Data Policy](docs/06-third-party-ai-and-data-policy.md) | CB-AIG-POL-002 | Due diligence, contract terms, monitoring, contingency and exit for AI suppliers | Word |
| 7 | [AI Risk Training Plan](docs/07-ai-risk-training-plan.md) | CB-AIG-TRN-001 | Role-based AI training for nine audiences, with access to CLARA tied to completion | Word |

## Highlights

- **Measurable tolerance.** The risk tolerance statement sets numeric limits (Gini, calibration, population stability, adverse impact ratio, override rate) that later parts test against.
- **No solely automated declines.** A design choice made in governance that shapes the EU AI Act, GDPR Article 22 and Consumer Credit Directive analysis.
- **Up-to-date regulation.** Dates reflect the Digital Omnibus on AI (Regulation (EU) 2026/1744), which moved Annex III high-risk obligations to 2 December 2027.
- **Working spreadsheets.** The Excel registers use drop-down lists, conditional formatting and live summary formulas.

## Folder layout

```
01-govern/
├── README.md
├── docs/    Markdown documents
└── files/   Word and Excel versions
```

## NIST AI RMF coverage

| Subcategory | Covered by |
| --- | --- |
| GOVERN 1.1 Legal and regulatory requirements | Obligations register |
| GOVERN 1.2 Trustworthy characteristics in policy | AI Governance Policy, section 3 |
| GOVERN 1.3, 1.4 Risk tolerance and risk management process | Risk tolerance statement; policy sections 5 and 6 |
| GOVERN 1.5 Ongoing monitoring and review | Policy gate G4; tolerance statement section 5 |
| GOVERN 1.6 AI system inventory | AI System Inventory |
| GOVERN 2.1, 2.3 Roles and executive accountability | RACI matrix |
| GOVERN 2.2 Training | AI Risk Training Plan |
| GOVERN 6.1, 6.2 Third-party risk and contingency | Third-party AI and data policy |

<!-- nav -->
---

[← Previous: Case file](../00-case-file/README.md) &nbsp;|&nbsp; [Repository home](../README.md) &nbsp;|&nbsp; [Next: AI Governance Policy →](docs/01-ai-governance-policy.md)
<!-- /nav -->
