# Trustworthiness Requirements Specification: CLARA

<!-- nav -->
[Repository home](../../README.md) › [Part 02: Map](../README.md) › Document 3 of 5
<!-- /nav -->

| Document control | |
| --- | --- |
| **Document ID** | CB-AIM-REQ-001 |
| **System** | AI-CR-001 CLARA |
| **Version** | 1.0 |
| **Owner** | Head of Credit Risk Analytics |
| **Reviewed by** | Model Risk Management; Compliance; Data Protection Officer; CISO |
| **Date** | 30 October 2026 |
| **Traceability matrix** | `files/CB-AIM-REQ-001_Requirements_Traceability_Matrix.xlsx` |

## 1. Purpose

This specification turns the AI Governance Policy principles, the risk tolerance limits and the impact assessment findings into **testable requirements** for CLARA. Every requirement has an acceptance criterion and a verification method, so Part 03 can test it and Part 04 can monitor it.

## 2. How to read the requirements

- **Priority:** *Must* requirements block go-live if not met; *Should* requirements may be accepted with an approved exception.
- **Verification:** **T** test, **A** analysis, **I** inspection of documents or configuration, **D** demonstration.
- **Source:** where the requirement comes from (policy, tolerance statement, impact assessment, law).

## 3. Requirements

### Valid and reliable

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-VR-01 | CLARA must separate good and bad risks better than Scorecard 19 | Gini at least 0.55 on out-of-time data, and higher than Scorecard 19 on the same data | T | Must | RTS-001 s.5 |
| REQ-VR-02 | Predicted default rates must match observed rates | Calibration within ±10% per grade on out-of-time data | T | Must | RTS-001 s.5 |
| REQ-VR-03 | Performance must hold across the main segments | Gini at least 0.50 for each of: Qatar, EU, new-to-bank, existing customers, personal loans, cards | T | Must | AIA IA-01 |
| REQ-VR-04 | Thin-file applicants must never be auto-approved or auto-recommended for decline | 0 thin-file cases outside the referral route in end-to-end testing | T | Must | AIA IA-03 |

### Safe

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-SF-01 | Decision routing must enforce grade and amount limits | 100% of test cases routed as specified in the profile, section 3 | T | Must | PRF-001 s.3 |
| REQ-SF-02 | CLARA must fail safe | If CLARA or a key input is unavailable, applications go to Scorecard 19 with manual review, never to automatic approval | D | Must | POL-001 s.8 |
| REQ-SF-03 | Out-of-range inputs must be rejected | Values outside validated ranges trigger referral and an alert | T | Must | Art. 15 |

### Secure and resilient

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-SR-01 | No known critical or high vulnerabilities at go-live | Clean vulnerability and dependency scan; penetration test findings closed | T | Must | RTS-001 s.5 |
| REQ-SR-02 | Model artefacts and training data protected against tampering | Signed model artefacts; write access restricted to the MLOps pipeline; changes logged | I | Must | Art. 15(5) |
| REQ-SR-03 | Resistant to manipulation of inputs | Robustness tests: small changes to inputs do not flip decisions unexpectedly; rate limits on repeated applications | T | Should | Art. 15(4) |
| REQ-SR-04 | Service availability | 99.5% availability in business hours; fallback within 5 minutes | T | Should | DORA |

### Accountable and transparent

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-AT-01 | Every decision must be logged | For each application: inputs, model version, PD, grade, reason codes, route, reviewer, final decision and timestamps, kept for at least 10 years | I, T | Must | Art. 12 |
| REQ-AT-02 | Technical documentation complete | Documentation covers every Annex IV item | I | Must | Art. 11 |
| REQ-AT-03 | Instructions for use issued to underwriters | Approved instructions covering purpose, limits, performance and oversight | I | Must | Art. 13 |
| REQ-AT-04 | Customers informed that AI supports the decision | Application journey and decision letters include the approved notice | I | Must | GDPR Art. 13; Art. 26(11) |

### Explainable

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-EX-01 | Every referral and recommended decline has reason codes | 100% coverage, four reason codes per case | T | Must | RTS-001 s.5 |
| REQ-EX-02 | Reason codes must reflect the real drivers | In a sample of 500 cases, the top reason code matches the largest SHAP contribution in at least 98% | A | Must | Art. 86 |
| REQ-EX-03 | Explanations understandable to customers | Plain-language templates in English and Arabic; comprehension test with at least 30 customers shows at least 80% understanding | D | Must | AIA IA-06 |

### Privacy-enhanced

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-PR-01 | Only necessary data used | Each of the 31 features justified in the data governance record; no special-category data as input | I | Must | GDPR Art. 5(1)(c) |
| REQ-PR-02 | Fairness-testing data kept separate | Protected attributes stored in a separate, access-controlled environment and never joined to the scoring pipeline | I | Must | GDPR Art. 9; AI Act Art. 10(5) |
| REQ-PR-03 | DPIA approved before go-live | Signed DPIA | I | Must | GDPR Art. 35 |
| REQ-PR-04 | Retention limits applied | Application data deleted or anonymised per the retention schedule | I | Should | GDPR Art. 5(1)(e) |

### Fair, with harmful bias managed

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-FR-01 | No protected characteristic or postcode used as an input | Feature list inspection and code review | I | Must | POL-001 s.4 |
| REQ-FR-02 | No feature acts as a strong proxy | Each feature's association with tested protected groups below the agreed threshold, or justified and approved | A | Must | AIA IA-02 |
| REQ-FR-03 | Approval rates fair across groups | Adverse impact ratio at least 0.80 for every tested group (target 0.90) | T | Must | RTS-001 s.5 |
| REQ-FR-04 | Equal treatment of applicants who repay | Equal opportunity difference no more than 5 percentage points | T | Must | RTS-001 s.5 |
| REQ-FR-05 | Thin-file segment reported separately | Separate fairness and performance results for applicants with less than 12 months of history | A | Must | AIA IA-03 |

### Human oversight

| ID | Requirement | Acceptance criterion | Verify | Priority | Source |
| --- | --- | --- | --- | --- | --- |
| REQ-HO-01 | Reviewers can override any recommendation | Override available on every case, with a mandatory reason | D | Must | Art. 14(4)(d) |
| REQ-HO-02 | Reviewers see what they need to judge the case | Review screen shows PD, grade, reason codes, key inputs and data-quality warnings | D | Must | Art. 14(4)(a) to (c) |
| REQ-HO-03 | Automatic decisions can be stopped | Authorised staff can switch off automatic approval within 15 minutes, routing all cases to manual review | D | Must | Art. 14(4)(e) |
| REQ-HO-04 | Only trained staff can review | Access granted only after "Working with CLARA" training is passed | I | Must | TRN-001 s.3 |

## 4. Summary

| Characteristic | Must | Should | Total |
| --- | --- | --- | --- |
| Valid and reliable | 4 | 0 | 4 |
| Safe | 3 | 0 | 3 |
| Secure and resilient | 2 | 2 | 4 |
| Accountable and transparent | 4 | 0 | 4 |
| Explainable | 3 | 0 | 3 |
| Privacy-enhanced | 3 | 1 | 4 |
| Fair | 5 | 0 | 5 |
| Human oversight | 4 | 0 | 4 |
| **Total** | **28** | **3** | **31** |

## 5. Change control

Requirements change only through the AI Governance Office. A changed *Must* requirement needs Model Risk Management and Compliance sign-off, and any affected tests must be re-run.

## Framework mapping

| This specification | NIST AI RMF | ISO/IEC 42001:2023 | EU AI Act |
| --- | --- | --- | --- |
| Requirements for trustworthy characteristics | MAP 1.6; MAP 2.2; MAP 3.4 | A.6.2.2 | Art. 9 to 15 |
| Testable acceptance criteria | MEASURE 1.1 | A.6.2.4 | Art. 9(8); Art. 15(1) |

<!-- nav -->
---

[← Previous: AI Impact Assessment: CLARA](02-ai-impact-assessment.md) &nbsp;|&nbsp; [Part 02: Map](../README.md) &nbsp;|&nbsp; [Next: Third-Party Component Register: CLARA →](04-third-party-component-register.md)
<!-- /nav -->
