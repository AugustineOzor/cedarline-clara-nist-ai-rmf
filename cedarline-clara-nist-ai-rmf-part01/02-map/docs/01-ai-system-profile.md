# AI System Profile: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 02: Map](../README.md) › Document 1 of 5
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIM-PRF-001 |
| **System** | AI-CR-001 CLARA (Credit Lending Automated Risk Assessment) |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics (system owner) |
| **Reviewed by** | Head of AI Governance; Model Risk Management |
| **Date** | 20 October 2026 |
| **Gate** | G1 Design (AI Governance Policy, section 6) |

## 1. Purpose

This profile describes what CLARA is for, who uses it, who it affects, how it works, where its limits are and what benefits are expected. It is the reference that every later assessment, test and decision about CLARA starts from.

## 2. Intended purpose

CLARA estimates the probability that an individual applying for an **unsecured personal loan or credit card** will default within 12 months, assigns a **risk grade** and recommends a **decision**. It supports, and does not replace, Cedarline's credit decision-making.

### In scope

- Individual applicants aged 18 or over applying through branches, the website or the mobile app
- Personal loans up to QAR 250,000 (EUR 60,000) and credit card limits up to QAR 100,000 (EUR 25,000)
- Qatar and EU (Ireland) retail lending

### Out of scope (not intended uses)

- Mortgages, SME and corporate lending
- Credit limit reductions, collections or account closure decisions
- Pricing (interest rate) decisions
- Marketing, pre-approval or "you may qualify" campaigns
- Applicants under 18, or joint applications

Using CLARA outside this scope requires a new impact assessment and AI Governance Committee approval.

## 3. How a decision is made

| Step | What happens | Who or what |
| --- | --- | --- |
| 1 | Customer submits application; identity and income documents are captured | Customer; DocRead extracts document data |
| 2 | Income and employment are verified | Verilytix verification API |
| 3 | Credit bureau report is retrieved | Qatar or Irish credit bureau |
| 4 | Policy rules run first (for example age, residency, existing default, fraud flags) | Credit decision engine (rules, not AI) |
| 5 | CLARA calculates PD, grade A to G and four reason codes | CLARA |
| 6 | Decision routing applied | Credit decision engine |
| 7 | Referred and recommended-decline cases are reviewed | Underwriter or credit officer |
| 8 | Customer is informed; for adverse outcomes, the main reasons and how to request a human review | Customer communications |

### Decision routing

| Risk grade | PD band | Amount | Route |
| --- | --- | --- | --- |
| A, B, C | Below 3% | Up to QAR 50,000 / EUR 12,500 | **Automatic approval** |
| A, B, C | Below 3% | Above that amount | Refer to underwriter |
| D, E | 3% to 10% | Any | Refer to underwriter |
| F, G | Above 10% | Any | **Recommended decline**, always reviewed by a credit officer before any decision |

## 4. Users and affected people

| Group | Role | Approx. size |
| --- | --- | --- |
| **Underwriters** | Review referred cases and make the final decision | 110 |
| **Credit officers** | Review every recommended decline; may approve, refer or decline | 30 |
| **Applicants** | Directly affected by the outcome | About 165,000 applications a year |
| **Existing customers** | Affected indirectly through credit availability and pricing of risk | 1.3 million |
| **Complaints handlers** | Explain decisions and arrange human reviews | 60 |

## 5. Model and data

| Item | Detail |
| --- | --- |
| **Model type** | Gradient-boosted decision trees (XGBoost 2.x), monotonic constraints on key risk drivers |
| **Target** | 90 or more days past due within 12 months of account opening |
| **Training data** | 412,000 applications approved between January 2020 and December 2024, with 12-month outcomes, from Qatar and Ireland |
| **Reject inference** | Applied to 96,000 declined applications from the same period, using bureau performance where available |
| **Features** | 31 features from five sources (application, bureau, internal history, verified income, product request) |
| **Excluded data** | Gender, nationality, religion, marital status, age, postcode and branch location are not model inputs |
| **Explanations** | SHAP values converted to plain-language reason codes from an approved library of 24 codes |
| **Retraining** | Annual, or earlier if monitoring limits are breached; every retrain goes through validation and the G2 gate |

### Main feature groups

| Group | Examples | Note |
| --- | --- | --- |
| Repayment history | Worst days past due in 12 months, missed payments in 24 months | Strongest predictors |
| Indebtedness | Debt-to-income ratio, card utilisation | Monotonic constraint: higher means riskier |
| Credit experience | Months since oldest account, active accounts | Can disadvantage people new to credit (see impact assessment) |
| Income and stability | Verified income, employment tenure, employer sector | Employer sector tested as a possible proxy for nationality |
| Relationship | Tenure with Cedarline, salary transferred to Cedarline | Can favour existing customers |
| Request | Amount, term, product | |

## 6. Expected benefits

| Benefit | Measure | Baseline (Scorecard 19) | Expected with CLARA |
| --- | --- | --- | --- |
| Better risk separation | Gini, out-of-time | 0.48 | 0.58 |
| Faster decisions | Share of applications decided automatically | 38% | 55% |
| Fewer bad loans | 12-month default rate on approved loans | 3.1% | 2.6% |
| More consistent decisions | Variation in underwriter outcomes for similar cases | High | Lower, with reasons recorded |
| Better explanations | Customers receiving specific reasons for adverse outcomes | Generic letter | Four specific reasons |

## 7. Known limits

1. **Thin files.** Applicants with less than 12 months of credit history get less reliable estimates. They are always referred, never auto-approved or auto-recommended for decline.
2. **Economic shocks.** Training data covers 2020 to 2024, including the pandemic period. A sudden downturn may change default patterns faster than annual retraining.
3. **Income volatility.** Self-employed and commission-based income is harder to verify and may be under-estimated.
4. **Explanations are approximations.** Reason codes summarise the main drivers, not the full model logic.
5. **Not a fraud model.** CLARA assumes application data is genuine; fraud controls run separately before it.

## 8. Dependencies

Credit bureaus (Qatar and Ireland), Verilytix, the cloud machine learning platform, the credit decision engine, DocRead and open-source libraries. All are listed with their risks and controls in the Third-Party Component Register (CB-AIM-TPC-001).

## 9. Related documents

AI Impact Assessment (CB-AIM-AIA-001), Trustworthiness Requirements (CB-AIM-REQ-001), Third-Party Component Register (CB-AIM-TPC-001), Initial Risk Identification (CB-AIM-RSK-001), and the Part 01 governance documents.

## Framework mapping

| This profile | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Intended purpose and scope | MAP 1.1; MAP 3.3 | A.6.2.2; A.9.4 | Art. 3(12); Art. 13(3)(b) |
| Users, setting and decision flow | MAP 1.1; MAP 3.4 | A.6.2.3 | Art. 13; Annex IV(1) |
| Benefits | MAP 3.1 | Clause 6.1.4 | Annex IV(2) |
| Known limits | MAP 2.2 | A.8.2 | Art. 13(3)(b)(ii) |
| Model and data description | MAP 2.1; MAP 2.3 | A.7.2; A.6.2.3 | Art. 11; Annex IV(2) |

<!-- nav -->
---

[← Previous: Part 02: Map overview](../README.md) &nbsp;|&nbsp; [Part 02: Map](../README.md) &nbsp;|&nbsp; [Next: AI Impact Assessment: CLARA →](02-ai-impact-assessment.md)
<!-- /nav -->
