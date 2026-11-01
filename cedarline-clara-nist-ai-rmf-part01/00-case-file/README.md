# Case File: Cedarline Bank and the CLARA Credit Model

<!-- nav -->
[Repository home](../README.md) › Case file
<!-- /nav -->

This case file holds the facts every document in this repository relies on. Cedarline Bank, its people, systems, customers and figures are **fictional** and were created for portfolio use.

## The organisation

| Item | Detail |
| --- | --- |
| **Name** | Cedarline Bank Q.P.S.C. |
| **Headquarters** | Doha, Qatar |
| **Business** | Retail and SME banking: current accounts, cards, personal loans, mortgages and SME lending |
| **Size** | About 3,400 employees and 1.1 million retail customers |
| **EU subsidiary** | Cedarline Bank Europe DAC, Dublin, Ireland: an authorised credit institution with about 210,000 retail customers |
| **Regulators** | Qatar Central Bank (group and Qatar operations); Central Bank of Ireland within the European banking supervision framework (EU subsidiary) |

## The AI system

| Item | Detail |
| --- | --- |
| **Name** | CLARA (Credit Lending Automated Risk Assessment) |
| **Inventory ID** | AI-CR-001 |
| **Purpose** | Estimates the 12-month probability of default (PD) for individual applicants for unsecured personal loans and credit cards, assigns a risk grade (A to G) and recommends approve, refer or decline |
| **Outputs** | PD, risk grade, decision recommendation and the four main reason codes behind each result |
| **Decision design** | Grades A to C up to QAR 50,000 (EUR 12,500 in the EU) may be approved automatically. Grades D and E, and all larger amounts, go to an underwriter. A recommended decline is **always reviewed by a credit officer**: CLARA never declines an applicant on its own. |
| **Model** | Gradient-boosted decision trees (XGBoost) with monotonic constraints, plus SHAP-based explanations |
| **Inputs** | Application data, internal account and repayment history, credit bureau data, and verified income and employment data |
| **Excluded inputs** | Gender, nationality, religion, marital status and other protected characteristics are never model inputs. Some are held separately, under a documented lawful basis, only for fairness testing. |
| **Build and hosting** | Developed in-house by the Credit Risk Analytics team; trained and served on a cloud machine learning platform, with Qatar and EU data processed in separate environments |
| **Third parties** | Credit bureaus in Qatar and Ireland; **Verilytix** (fictional) income and employment verification API; the cloud platform provider; open-source libraries (XGBoost, SHAP, scikit-learn) |
| **Volume** | About 165,000 applications a year (120,000 Qatar, 45,000 EU) |
| **Expected decision mix** | About 55% approved automatically, 30% referred, 15% recommended for decline |
| **Replaces** | A 2019 logistic-regression scorecard ("Scorecard 19"), which stays available as the fallback |
| **Lifecycle stage** | Validation and pilot. Qatar go-live planned for Q3 2027; EU go-live after conformity assessment and before **2 December 2027** |

## Why CLARA is a high-risk AI system

AI systems used to evaluate the creditworthiness of individuals or establish their credit score are listed as **high-risk** in Annex III, point 5(b), of the EU AI Act (Regulation (EU) 2024/1689). Following the Digital Omnibus on AI (Regulation (EU) 2026/1744), obligations for Annex III high-risk systems apply from **2 December 2027**. Because Cedarline builds CLARA and uses it under its own name, the bank is both the **provider** and the **deployer**.

Internally, CLARA is rated **Tier 1**, the highest of Cedarline's three AI risk tiers, because it makes or shapes decisions with significant financial effects on individuals.

## Governance structure

| Body or role | Responsibility for CLARA |
| --- | --- |
| **Board Risk Committee** | Approves the AI risk tolerance statement; receives quarterly AI risk reporting |
| **AI Governance Committee (AIGC)** | Chaired by the Chief Risk Officer; meets monthly; approves AI policy, Tier 1 go/no-go decisions and risk acceptances |
| **Chief Risk Officer (CRO)** | Senior executive accountable for AI risk across the group |
| **Head of AI Governance** | Runs the AI governance programme and maintains the AI system inventory |
| **Head of Credit Risk Analytics** | System owner and model owner for CLARA |
| **Model Risk Management (MRM)** | Independent model validation (second line) |
| **Data Protection Officer (DPO)** | Data protection impact assessment and data subject rights |
| **Head of Compliance** | Regulatory obligations and fair lending |
| **Chief Information Security Officer (CISO)** | Security of the AI platform and data |
| **Head of Retail Credit Operations** | Underwriters and credit officers who review CLARA's referrals and recommended declines |
| **Internal Audit** | Independent assurance (third line) |

## Frameworks used

- **NIST AI Risk Management Framework (AI RMF 1.0)**: the organising framework for this repository (Govern, Map, Measure, Manage)
- **EU AI Act**, as amended by the Digital Omnibus on AI
- **ISO/IEC 42001:2023** (AI management systems), used for crosswalks
- **GDPR**, the EU **Consumer Credit Directive** (EU) 2023/2225 and the EBA Guidelines on loan origination and monitoring (EBA/GL/2020/06)
- **Qatar Personal Data Privacy Protection Law** (Law No. 13 of 2016) and Qatar Central Bank requirements

<!-- nav -->
---

[← Repository home](../README.md) &nbsp;|&nbsp; [Next: Part 01: Govern →](../01-govern/README.md)
<!-- /nav -->
