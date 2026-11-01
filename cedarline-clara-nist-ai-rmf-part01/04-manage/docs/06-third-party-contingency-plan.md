# Third-Party AI Contingency Plan: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 04: Manage](../README.md) › Document 6 of 7
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIMG-TCP-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Procurement and Third-Party Risk, with the Head of Credit Risk Analytics |
| **Approved by** | AI Governance Committee, 26 November 2026 |
| **Test frequency** | Every year, and after any change to a critical supplier |

## 1. Purpose

CLARA depends on outside data, services and software (Third-Party Component Register, CB-AIM-TPC-001). This plan sets what Cedarline does when one of them fails, changes, is withdrawn or causes an incident, so that customers keep getting fair, timely decisions.

## 2. Scenarios

| # | Scenario | Component | Detection | Immediate action | Recovery target | Decision authority |
| --- | --- | --- | --- | --- | --- | --- |
| C-01 | Credit bureau outage (Qatar or Ireland) | TPC-01, TPC-02 | API errors; supplier notice | Affected applications held and then sent to manual review; customers told of delay | Decisions within 2 working days of bureau recovery | CLARA duty manager |
| C-02 | Bureau data error affecting many records | TPC-01, TPC-02 | Data-quality checks; spike in disputes or overrides | Pause automatic approvals for affected market; identify affected decisions | Re-review affected decisions within 10 working days | Head of Credit Risk Analytics |
| C-03 | Verilytix outage | TPC-03 | API errors | Manual income verification; automatic approval suspended for affected applications | Service restored, or manual process at full capacity within 1 day | CLARA duty manager |
| C-04 | Verilytix changes its method without notice | TPC-03 | M-15 mismatch rate; PSI shift on income features | Pause use of Verilytix income in automatic approvals; revalidate | Revalidation within 20 working days | Head of Credit Risk Analytics |
| C-05 | Verilytix exits the market or contract terminated | TPC-03 | Supplier notice; financial distress signals | Activate alternative supplier from pre-qualified shortlist; manual verification meanwhile | Alternative live within 90 days | AI Governance Committee |
| C-06 | Cloud platform regional outage | TPC-04 | Monitoring alerts | Fall back to Scorecard 19 on-premises | Fallback within 30 minutes; CLARA restored within 24 hours | Head of Credit Risk Analytics |
| C-07 | Critical vulnerability in an open-source library | TPC-05 to TPC-07 | Dependency scanning; security advisories | Assess exploitability within 24 hours; patch, or fall back if exploitable | Fix deployed within 7 days for critical findings | CISO |
| C-08 | Supplier security incident involving our data | Any | Supplier notice (24-hour contract term) | Incident response under CB-AIMG-IRP-001; assess personal data breach | As set by the incident procedure | CISO; DPO |

## 3. Pre-agreed fallbacks

- **Scorecard 19** stays deployable on-premises until CLARA's 12-month revalidation is passed.
- **Manual underwriting** capacity: Retail Credit Operations can handle up to 100% of Qatar volume for 5 working days by redeploying trained staff, with overtime cover after that.
- **Alternative verification supplier:** two suppliers pre-qualified through due diligence; contract terms agreed in principle.

## 4. Customer impact rules

During any contingency:

1. No applicant is declined because a supplier failed. Cases wait for manual review instead.
2. Customers are told about delays within one working day.
3. Decisions made on bad supplier data are re-reviewed, and customers are told the outcome.

## 5. Testing

| Test | Frequency | Last result |
| --- | --- | --- |
| Failover to Scorecard 19 | Every year | 3 minutes 40 seconds (shadow pilot, October 2026) |
| Verilytix outage simulation | Every year | Passed in pre-production testing (T-06) |
| Tabletop: supplier method change (C-04) | Every year | Scheduled for Q1 2027 |
| Alternative supplier activation walkthrough | Every two years | Scheduled for Q3 2027 |

## Framework mapping

| This plan | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act and other |
| --- | --- | --- | --- |
| Contingency for third-party failures | GOVERN 6.2; MANAGE 3.1 | A.10.3 | DORA Art. 28(8) |
| Monitoring of third-party components | MANAGE 3.2 | A.10.3 | AI Act Art. 25 |

<!-- nav -->
---

[← Previous: Post-Deployment Monitoring and Continuous Improvement Plan: CLARA](05-post-deployment-monitoring-plan.md) &nbsp;|&nbsp; [Part 04: Manage](../README.md) &nbsp;|&nbsp; [Next: AI System Decommissioning Procedure →](07-ai-system-decommissioning-procedure.md)
<!-- /nav -->
