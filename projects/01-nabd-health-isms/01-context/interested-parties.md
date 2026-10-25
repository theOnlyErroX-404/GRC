# Interested Parties and Their Requirements

| Field | Value |
|---|---|
| Document ID | NH-CTX-002 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 20 November 2026 |
| Owner | ISMS Lead Implementer |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This document is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This document identifies the interested parties relevant to the ISMS, their needs and
expectations, the requirements Nabd Health has agreed to meet, and how the ISMS responds
to them (ISO/IEC 27001:2022 clauses 4.2 and 4.3). Contractual and legal entries are
summaries for the simulation and are not legal advice.

## 2. Method

Parties were identified from the fact base, customer contracts, supplier list, employment
records, and the project's legal context. Each requirement is classified as:

- **L** — legal or regulatory
- **C** — contractual
- **B** — business or stakeholder expectation
- **V** — voluntary commitment (policy, certification, insurer condition)

Requirements are reviewed at least annually and when a contract, regulation, or
stakeholder changes. The owner is accountable for confirming that the requirement
remains current and that the ISMS response is effective.

## 3. Register of interested parties

| ID | Party | Type | Needs and expectations | Requirement source | Type | ISMS response | Communication | Review | Owner |
|---|---|---|---|---|---|---|---|---|---|
| IP-01 | Patients | External | Confidentiality of health data; availability of records and video visits; clear privacy information | PDPL 151/2020; published privacy policy; terms of service | L, C, B | Access control, encryption, incident response, continuity, privacy policy, data subject request procedure | Privacy notice, service status, breach notification where required | Annual | CPO |
| IP-02 | Clinics | External | Protection of their patient data; platform availability; breach notification; audit rights | Customer contracts, DPAs | C | ISMS scope, access control, backup and recovery, incident response, supplier controls, right-to-audit support | Account management, security questionnaire answers, incident updates | Annual | COO |
| IP-03 | Hospital groups | External | ISO/IEC 27001 certification or credible timeline; 99.9 percent availability; 72-hour breach notification in five contracts; audit rights in three | Tender requirements and hospital contracts | C | Certification programme, KPIs, incident response, internal audit, management review | Tender responses, certification evidence, contract reviews | Annual | CEO |
| IP-04 | Employees | Internal | Fair processing of their data; clear security rules; safe working environment; ability to report concerns without blame | Employment contracts, employee handbook, PDPL | L, C, B | HR security policy, acceptable use, awareness programme, incident reporting channel, access control | Intranet, onboarding, awareness sessions | Annual | HR Manager |
| IP-05 | Outsourced developers (Pixelwave) | External | Clear security and confidentiality obligations; access to what they need | Services agreement (to be revised) | C | Supplier security policy, contractor agreement, access control, secure development, offboarding | Contract review, onboarding, access reviews | Annual | CTO |
| IP-06 | Executives and board | Internal | Contract wins, investor confidence, controlled cost, no major incidents | Fiduciary duty, business plan | B | Risk register, management review, KPIs, incident reporting, budget | Board reporting, management review minutes | Quarterly | CEO |
| IP-07 | Investors | External | Security due diligence; evidence of risk management; no material incidents | Investment agreements, due diligence questionnaires | C, B | ISMS documentation, risk treatment, internal audit, KPIs | Due diligence responses, management review summary | Annual / on request | CEO |
| IP-08 | Data protection authority | External | Lawful processing, security measures, breach notification, records of processing, cross-border safeguards | PDPL 151/2020 and executive regulations | L | Privacy policy, records of processing, DPIA, incident response, supplier DPAs, transfer assessment | Regulatory notifications and filings | Annual | CFO |
| IP-09 | Ministry of Health and Population | External | Compliance with health data and telemedicine rules | Ministry rules (to be confirmed by counsel) | L | Scope controls, clinical data handling, retention, incident response | Regulatory correspondence | Annual | CFO |
| IP-10 | Central Bank of Egypt | External | Compliance for payment flows | CBE requirements (to be confirmed) | L | Payment data kept at PayNile; supplier assurance; no card data stored | Regulatory correspondence | Annual | CFO |
| IP-11 | Cyber insurer | External | Accurate declarations; minimum controls such as MFA and backups | Insurance policy and application | C, V | Corrected declaration, MFA enforcement, backup testing, incident notification | Renewal declaration, incident notification | Annual | CFO |
| IP-12 | Certification body | External | A conforming ISMS and objective evidence | ISO/IEC 27001:2022 certification agreement | V | Full ISMS documentation, internal audit, management review, corrective actions | Stage 1 and Stage 2 audits | Annual | ISMS Manager |
| IP-13 | Critical suppliers (AWS, GitHub, Google, SMSGate, VideoBridge, PayNile, and others) | External | Clear requirements; timely incident information; lawful data handling | Supplier agreements and DPAs | C | Supplier register, due diligence, contract clauses, service reviews, exit planning | Supplier reviews, security contacts | Annual or on change | CFO |
| IP-14 | Landlord (Cairo Tower Facilities) | External | Compliance with lease and building rules; no damage; cooperation on incidents | Lease agreement | C | Physical security policy, visitor and access coordination, incident escalation | Building management contact | Annual | Office Manager |
| IP-15 | External law firm | External | Lawful instructions; confidentiality | Engagement letter | C | Confidentiality terms, need-to-know access, supplier controls | Engagement correspondence | Annual | CFO |
| IP-16 | Regulators and law enforcement (cyber crime) | External | Cooperation and lawful handling of electronic evidence | Law 175/2018 | L | Incident response, evidence collection, log retention | Formal requests through counsel | Annual | CFO |

## 4. Priority requirements

The following requirements have the greatest influence on the ISMS scope and risk
criteria. They are traced to the risk register where they create uncertainty.

| ID | Requirement | Source | Consequence of failure | Linked risks |
|---|---|---|---|---|
| REQ-01 | Protect confidentiality and integrity of patient health data | PDPL, customer DPAs, patient expectation | Regulatory penalty, contract termination, patient harm, reputational damage | R-04, R-12, R-21, R-22 |
| REQ-02 | Notify affected hospital customers of a breach within 72 hours (5 contracts) | Hospital contracts | Contractual breach, loss of hospital accounts | R-11 |
| REQ-03 | Meet 99.9 percent availability in 9 contracts | Customer contracts | Service credits, churn, tender disqualification | R-03, R-23 |
| REQ-04 | Achieve ISO/IEC 27001 certification or demonstrate a credible timeline | 3 hospital tenders | Loss of tenders and revenue growth | R-13 |
| REQ-05 | Enforce MFA as declared to the insurer | Insurance application | Cover voided or claim refused | R-01 |
| REQ-06 | Assess and safeguard cross-border transfer of patient data to Bahrain | PDPL | Regulatory action; suspension of hosting arrangement | R-22 |
| REQ-07 | Remove access promptly when staff or contractors leave | PDPL, customer contracts, employment terms | Unauthorized access; audit nonconformity | R-02 |
| REQ-08 | Provide audit rights and security evidence to hospital customers | 3 hospital contracts | Failed audit; contract termination | R-13, R-15 |

## 5. Communication arrangements

| Audience | What | When | Channel | Owner |
|---|---|---|---|---|
| All staff | Security policy, awareness, incident reporting expectations | Onboarding and quarterly | Email, intranet, awareness sessions | HR Manager / ISMS Manager |
| Executives and board | Risk profile, incidents, KPI performance | Quarterly and after major incidents | Management review, board pack | CEO |
| Clinics and hospitals | Security questionnaire responses, incident notifications, certification status | On request and per contract | Account management, formal notice | COO |
| Patients | Privacy notice, material service or data incidents | On publication and when required | Website, app notice, direct notification | CPO |
| Regulators | Notifications and filings | As required by law | Formal regulatory channel via counsel | CFO |
| Suppliers | Security requirements, incident coordination, reviews | At onboarding, annually, and on change | Contract, review meeting, security contact | CFO |
| Certification body | Audit evidence and corrective action updates | Audit cycle | Audit portal and meetings | ISMS Manager |

## 6. Review and revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 20 November 2026 | Initial interested-party register | ISMS Lead Implementer |

Next scheduled review: November 2027, or earlier after a material contract, regulatory,
or organizational change.
