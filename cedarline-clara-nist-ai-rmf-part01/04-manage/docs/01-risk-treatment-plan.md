# AI Risk Treatment Plan: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 1 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-RTP-001 |
| **System** | AI-CR-001 CLARA, model version 1.2 |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Tracker** | `files/CB-AIMG-RTP-001_Risk_Treatment_Tracker.xlsx` |

## 1. Purpose

Five risks in the AI Risk Register (CB-AIMS-RR-001) remain **Medium** after controls. This plan sets the response to each one: the actions, owners, resources, deadlines and how success will be measured. Low residual risks are accepted and covered by routine monitoring.

## 2. Summary

| Risk | Residual | Response | Target residual | Target date |
| --- | --- | --- | --- | --- |
| R-03 Thin-file applicants disadvantaged | 9 Medium | Mitigate | 6 Low | 31 December 2027 |
| R-16 EU deadline missed or conformity incomplete | 10 Medium | Mitigate | 5 Low | 31 October 2027 |
| R-02 Proxies for protected characteristics | 8 Medium | Mitigate | 4 Low | 30 June 2027 |
| R-07 Automation bias by reviewers | 8 Medium | Mitigate | 4 Low | 30 April 2027 |
| R-01 Model less accurate than expected | 8 Medium | Mitigate | 6 Low | 31 March 2028 |

## 3. Treatment by risk

### R-03 Thin-file applicants disadvantaged

**Why it remains Medium.** The adverse impact ratio for thin-file expatriates improved from 0.76 to 0.83 but is still amber, below the 0.90 target.

| # | Action | Owner | Due | Resources |
| --- | --- | --- | --- | --- |
| 3.1 | Extend alternative data (verified rent, utility and telecom payment history, with consent) to all thin-file applicants | Head of Credit Risk Analytics | 30 June 2027 | 2 data scientists; supplier contract |
| 3.2 | Introduce a "credit starter" card product with lower limits for thin-file applicants who would otherwise be declined | Head of Retail Lending | 30 September 2027 | Product team |
| 3.3 | Monthly intersectional fairness report for thin-file segments | Model Risk Management | From go-live | Existing team |
| 3.4 | Underwriter guidance on assessing thin-file applications | Head of Retail Credit Operations | 31 March 2027 | Training team |

**Success measure.** AIR for every thin-file segment at least 0.90 for three consecutive months, with default rates within calibration limits.

### R-16 EU deadline missed or conformity incomplete

**Why it remains Medium.** Three *Must* requirements are open (technical documentation, instructions for use, DPIA), and the conformity assessment and EU database registration have not started.

| # | Action | Owner | Due | Resources |
| --- | --- | --- | --- | --- |
| 16.1 | Approve the DPIA | Data Protection Officer | 28 February 2027 | DPO team |
| 16.2 | Complete the remaining 3 of 17 Annex IV documentation items | Head of Credit Risk Analytics | 30 June 2027 | Technical writer |
| 16.3 | Issue instructions for use to underwriters | Head of Credit Risk Analytics | 31 July 2027 | With Credit Operations |
| 16.4 | Complete the fundamental rights impact assessment | Head of Compliance | 30 September 2027 | Compliance; Legal |
| 16.5 | Internal-control conformity assessment, EU declaration of conformity and database registration | Head of AI Governance | 31 October 2027 | External legal review budget |

**Success measure.** All items complete at least one month before 2 December 2027; Internal Audit review of the conformity file with no high findings.

### R-02 Proxies for protected characteristics

**Why it remains Medium.** All features now pass proxy testing, but new proxies could emerge as the applicant population changes.

| # | Action | Owner | Due |
| --- | --- | --- | --- |
| 2.1 | Automate quarterly proxy testing of all features in the monitoring pipeline | Model Risk Management | 31 March 2027 |
| 2.2 | Require proxy testing for any new feature before it enters development | Head of Credit Risk Analytics | 31 January 2027 |
| 2.3 | External fairness review of CLARA by an independent specialist | Head of Compliance | 30 June 2027 |

**Success measure.** No feature above 0.30 association in four consecutive quarterly tests; external review with no material findings.

### R-07 Automation bias by reviewers

**Why it remains Medium.** Reviewer behaviour could not be measured in shadow mode.

| # | Action | Owner | Due |
| --- | --- | --- | --- |
| 7.1 | Weekly override-rate report by reviewer for the first three months of live use | Head of Retail Credit Operations | From go-live |
| 7.2 | Monthly quality review of 50 randomly selected agreed declines and 50 overrides | Credit Quality Assurance | From go-live |
| 7.3 | Hide CLARA's recommendation until the reviewer has looked at the key application data, for recommended declines only | Head of Credit Risk Analytics | 31 March 2027 |
| 7.4 | Refresher training for reviewers outside the green band | Head of Retail Credit Operations | Within 30 days of each finding |

**Success measure.** Override rate in the 3% to 15% green band for three consecutive months; quality reviews find no unjustified agreed declines.

### R-01 Model less accurate than expected

**Why it remains Medium.** Validation results are strong, but they are based on 2025 data, and calibration can only be confirmed after 12 months of live outcomes.

| # | Action | Owner | Due |
| --- | --- | --- | --- |
| 1.1 | Early-warning arrears indicators (3-month and 6-month) by grade | Head of Credit Risk Analytics | From go-live |
| 1.2 | Full revalidation after 12 months of live data | Model Risk Management | 31 March 2028 |
| 1.3 | Keep Scorecard 19 available as fallback until revalidation passes | Head of Credit Risk Analytics | Until 31 March 2028 |

**Success measure.** Early-warning indicators within expected ranges; revalidation confirms Gini at least 0.55 and calibration within ±10%.

## 4. Governance

- Progress is tracked in the treatment tracker and reported to the AI Governance Committee monthly.
- An action more than 30 days overdue is escalated to the Chief Risk Officer.
- A risk is reduced to its target rating only after its success measure is met and Model Risk Management agrees.

## Framework mapping

| This plan | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Risk responses planned and resourced | MANAGE 1.3; MANAGE 2.1 | Clause 6.1.3; 8.3 | Art. 9(2)(d); 9(4) |
| Residual risk documented | MANAGE 1.4 | Clause 8.3 | Art. 9(5) |

<!-- nav -->
---

[← Previous: Part 04: Manage overview](../README.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: Human Oversight, Override and Stop Procedure: CLARA →](02-human-oversight-procedure.md)
<!-- /nav -->
