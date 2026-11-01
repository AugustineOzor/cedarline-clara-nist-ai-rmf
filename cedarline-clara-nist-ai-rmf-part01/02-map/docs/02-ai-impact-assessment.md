# AI Impact Assessment: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 02: Map](../README.md) › Document 2 of 5
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIM-AIA-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Contributors** | Compliance, Data Protection Officer, Retail Credit Operations, Model Risk Management, Customer Experience, Information Security |
| **Approved by** | AI Governance Committee, 28 October 2026 |
| **Next review** | Before G3 go-live, then every year or after a material change |

## 1. Purpose

This assessment asks how CLARA could help or harm the people it affects, the bank and society, and what Cedarline will do about it. It informs the risk register in Part 03 and the decision on whether CLARA should go live.

It is linked to, but does not replace, the **data protection impact assessment** (GDPR Article 35, owned by the DPO) and the **fundamental rights impact assessment** that Cedarline must complete as a deployer before first use in the EU (EU AI Act Article 27). Findings are shared across all three to avoid gaps.

## 2. Method

1. Identify everyone who could be affected, using the profile (CB-AIM-PRF-001).
2. Hold workshops with credit operations, complaints, compliance and customer experience teams, and review two years of credit-decision complaints.
3. Rate each impact for **severity** (1 to 5) and **likelihood** (1 to 5) before and after mitigation, using the scales in the AI Risk Tolerance Statement.
4. Compare CLARA with the non-AI alternative: keeping Scorecard 19 with manual underwriting.

## 3. Who is affected

| Stakeholder | How they are affected |
| --- | --- |
| Applicants | Access to credit, the amount offered and the speed of the decision |
| Groups of applicants (see section 5) | May be systematically affected if the model is less accurate for them |
| Underwriters and credit officers | Workload, decision quality, and risk of over-relying on CLARA |
| Existing customers | Indirectly, through the bank's credit losses and lending appetite |
| Cedarline Bank | Credit losses, efficiency, regulatory and reputational exposure |
| Society | Financial inclusion; responsible lending and over-indebtedness |

## 4. Benefits

| Benefit | Who gains | Evidence |
| --- | --- | --- |
| Faster decisions: 55% decided automatically, against 38% today | Applicants, the bank | Pilot results |
| Fewer people lent money they cannot repay | Applicants, society | Default rate on approved loans expected to fall from 3.1% to 2.6% |
| More consistent decisions with recorded reasons | Applicants, regulators | Reason codes on every referral and decline |
| Specific reasons for adverse outcomes, instead of a generic letter | Applicants | Explanation design |
| Underwriters focus on complex cases | Staff | Workload model |

## 5. Potential harms and groups at risk

| ID | Potential harm | Most affected | Severity | Likelihood | Inherent rating |
| --- | --- | --- | --- | --- | --- |
| IA-01 | Wrongful decline or lower limit because of model error | Applicants | 4 | 3 | **12 High** |
| IA-02 | Unfair outcomes because of proxies for protected characteristics in the data (for example employer sector correlating with nationality) | Expatriate applicants; women | 5 | 3 | **15 Critical** |
| IA-03 | Applicants new to credit are scored as higher risk because they have little history, not because they are risky | Young people; newly arrived expatriates | 4 | 4 | **16 Critical** |
| IA-04 | Irregular income under-estimated | Self-employed and commission-based workers | 3 | 3 | **9 Medium** |
| IA-05 | Historical bias in past approvals repeated, because the model learns from loans the bank chose to approve | Groups previously under-served | 4 | 3 | **12 High** |
| IA-06 | Customers cannot understand or challenge a decision | All applicants; customers with lower financial literacy or limited English or Arabic | 4 | 2 | **8 Medium** |
| IA-07 | Underwriters accept recommendations without real scrutiny (automation bias) | Applicants in referred and declined cases | 4 | 3 | **12 High** |
| IA-08 | Over-lending if the model under-estimates risk in a downturn | Applicants (over-indebtedness); the bank | 4 | 2 | **8 Medium** |
| IA-09 | Misuse outside the intended purpose, for example for pricing or limit cuts | Existing customers | 4 | 2 | **8 Medium** |
| IA-10 | Personal data used beyond what is needed, or exposed in a breach | Applicants | 4 | 2 | **8 Medium** |
| IA-11 | Applicants refused because a supplier (bureau or verification service) returns wrong data | Applicants | 3 | 2 | **6 Low** |

Ratings: severity × likelihood. 1 to 6 Low, 7 to 10 Medium, 11 to 14 High, 15 to 25 Critical.

## 6. Fundamental rights considered

| Right | Relevance to CLARA |
| --- | --- |
| Non-discrimination | IA-02, IA-03, IA-05 |
| Protection of personal data | IA-10 |
| Access to essential services (credit) | IA-01, IA-03, IA-04 |
| Right to an effective remedy and to be heard | IA-06; human review and complaints routes |
| Consumer protection | IA-08; responsible lending |

## 7. Mitigations and residual impact

| ID | Key mitigations | Owner | Residual rating |
| --- | --- | --- | --- |
| IA-01 | Validation thresholds; human review of every recommended decline; customer right to human review | Head of Credit Risk Analytics | 6 Low |
| IA-02 | Protected characteristics and postcode excluded; proxy testing of every feature; fairness limits (adverse impact ratio at least 0.80, target 0.90); quarterly fairness monitoring | Head of Credit Risk Analytics; Compliance | 8 Medium |
| IA-03 | Thin-file applicants always referred; alternative data considered (salary transfer, rent and utility history with consent); separate monitoring of this segment | Head of Retail Credit Operations | 8 Medium |
| IA-04 | Underwriter guidance for irregular income; additional evidence accepted | Head of Retail Credit Operations | 6 Low |
| IA-05 | Reject inference; comparison against declined-applicant bureau outcomes; fairness testing on historical declines | Head of Credit Risk Analytics | 8 Medium |
| IA-06 | Plain-language reason codes in English and Arabic; clear route to a human review; complaints handler training | Head of Compliance | 4 Low |
| IA-07 | Override rate monitoring (green band 3% to 15%); training and assessment before access; reviewers must record reasons when they agree with a decline | Head of Retail Credit Operations | 6 Low |
| IA-08 | Monthly calibration and stability monitoring; economic early-warning triggers; fallback to Scorecard 19 | Head of Credit Risk Analytics | 6 Low |
| IA-09 | Purpose limits in the profile and instructions for use; access controls; inventory change control | Head of AI Governance | 4 Low |
| IA-10 | Data minimisation; DPIA; encryption; access logging; retention limits | Data Protection Officer; CISO | 4 Low |
| IA-11 | Supplier data-quality checks; applicants can correct bureau data; contingency routing | Procurement; Head of Retail Credit Operations | 3 Low |

Three impacts remain **Medium** after mitigation (IA-02, IA-03 and IA-05, each rated 8). They are within tolerance only if the fairness limits in CB-AIG-RTS-001 are met in testing (Part 03) and monitored after go-live.

## 8. Non-AI alternative

Keeping Scorecard 19 with manual underwriting avoids some model risks but performs worse on almost every measure: lower accuracy (Gini 0.48), slower decisions, generic decline reasons and greater variation between underwriters. It also carries bias risk, because it has never been formally fairness-tested. **CLARA, with the mitigations above, is expected to produce fairer and more accurate outcomes than the alternative**, provided the testing in Part 03 confirms it.

## 9. Conclusion

**Proceed to development and validation, with conditions:**

1. Fairness testing in Part 03 must show adverse impact ratios of at least 0.80 for every tested group, and the thin-file segment must be reported separately.
2. The fundamental rights impact assessment (Article 27) and the DPIA must be approved before the G3 go-live decision.
3. Arabic and English explanation templates must be tested with customers before go-live.
4. This assessment must be re-run if the intended purpose, data sources or decision routing change.

## Framework mapping

| This assessment | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Impacts on individuals, groups and society | MAP 1.1; MAP 5.1 | Clause 6.1.4; A.5.2 to A.5.5 | Art. 9(2)(a); Art. 27 |
| Benefits and costs, including non-AI alternative | MAP 3.1; MAP 3.2 | A.5.2 | Annex IV(2) |
| Stakeholder engagement | MAP 5.2; GOVERN 5.1 | A.5.5 | Art. 27(1) |
| Bias and fairness risks | MAP 2.3; MEASURE 2.11 | A.7.4 | Art. 10(2)(f) |

<!-- nav -->
---

[← Previous: AI System Profile: CLARA](01-ai-system-profile.md) &nbsp;|&nbsp; [Part 02: Map](../README.md) &nbsp;|&nbsp; [Next: Trustworthiness Requirements Specification: CLARA →](03-trustworthiness-requirements.md)
<!-- /nav -->
