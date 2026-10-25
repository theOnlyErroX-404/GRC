# Nabd Health ISMS: Simulated ISO/IEC 27001:2022 Implementation

| Field | Value |
|---|---|
| Project | 01: Nabd Health ISMS |
| Standard | ISO/IEC 27001:2022 (including Amendment 1:2024) |
| Simulated timeline | November 2026 to April 2027 |
| Status | In progress: artifacts below are drafted; closing items remain |
| Classification | Internal (simulated client confidential) |

> **Everything here is fictional.** Nabd Health, its people, systems, suppliers,
> incidents, and data are invented for a simulated implementation. Nothing in this
> project describes a real client, employer, audit, or certification. Any resemblance to
> a real organization is coincidental.

## 1. The client

Nabd Health for Digital Health Solutions S.A.E. is a fictional Egyptian health-tech
company founded in 2021. It provides a multi-tenant SaaS platform for private clinics and
small hospitals: appointment booking, electronic patient records, telemedicine, billing,
a patient mobile app, and an internal Admin Panel.

| Fact | Value |
|---|---|
| Headquarters | 5th Settlement, New Cairo, Egypt |
| Headcount | 60 employees plus 3 outsourced mobile developers |
| Customers | 118 clinics and 6 hospital groups |
| Patient records | About 412,000 records and 6.5 TB of files |
| Hosting | AWS Middle East (Bahrain, me-south-1) |
| Driver for the ISMS | Three hospital tenders requiring ISO 27001, Series B due diligence, PDPL obligations, and a 2026 phishing incident |

The full baseline is in [00-company-fact-base.md](00-company-fact-base.md). It is the
single source of truth; every risk, control, and finding in this project traces to it.

## 2. What the project demonstrates

This simulated ISMS engagement covers the following areas; it is not a document template pack:

- **Context and scope** derived from contracts, data flows, and a 22-gap baseline.
- **Risk assessment** with a defined 5×5 methodology, 26 risks, and traceability from
  gap to asset to Annex A control to treatment.
- **Statement of Applicability** covering all 93 Annex A controls, with two justified
  exclusions and honest implementation status.
- **13 topic-specific policies and operational documents** written for a 60-person
  cloud-native company, not copied from an enterprise template.
- **Evidence** for access, backups, continuity, incidents, awareness, suppliers, and
  privacy.
- **Simulated internal audit** with three minor nonconformities, four observations, and
  two improvement opportunities. Because this is a simulation, the auditor is a
  fictional role played by the same author; it is not a real independent audit.
- **Management review** with decisions, owners, and due dates.
- **Corrective action log** connecting audit findings to owners and closure evidence.

## 3. Timeline (simulated)

| Phase | Date | Output |
|---|---|---|
| Discovery and fact base | October 2026 | Company fact base (NH-FB-001) |
| Context and scope | November 2026 | NH-CTX-001 to NH-CTX-003 |
| Leadership and policy | December 2026 | Information security policy; roles and RACI |
| Risk assessment | January 2027 | Methodology, asset register, risk register |
| Treatment and SoA | January–February 2027 | Treatment plan; 93-control SoA; 13 policies |
| Implementation and evidence | February–March 2027 | Procedures, access reviews, restore test, supplier register, awareness |
| Simulated internal audit | 12–16 April 2027 | Audit report and findings (23 April 2027) |
| Management review | 29 April 2027 | Decisions and certification application |
| Nabd Health's planned Stage 1 audit | June 2027 (fictional) | Certification readiness |

Simulation time is separate from the repository's real creation date, as defined in
Section 19 of the fact base.

## 4. Document index

### Foundation

| ID | Document | Status |
|---|---|---|
| NH-FB-001 | [Company fact base](00-company-fact-base.md) | Baseline v1.0 |
| NH-CTX-001 | [Context of the organization and issues](01-context/context-and-issues.md) | Approved |
| NH-CTX-002 | [Interested parties and requirements](01-context/interested-parties.md) | Approved |
| NH-CTX-003 | [ISMS scope](01-context/isms-scope.md) | Approved |

### Leadership

| ID | Document | Status |
|---|---|---|
| NH-POL-001 | [Information security policy](02-leadership/information-security-policy.md) | Approved |
| NH-ROL-001 | [Roles, responsibilities and RACI](02-leadership/roles-and-responsibilities.md) | Approved |

### Risk management

| ID | Document | Status |
|---|---|---|
| NH-RISK-001 | [Risk assessment and treatment methodology](03-risk/risk-methodology.md) | Approved |
| NH-REG-001 | [Asset register](03-risk/asset-register.csv) | 50 assets |
| NH-REG-002 | [Risk register](03-risk/risk-register.csv) | 26 risks |
| NH-PLN-001 | [Risk treatment plan](03-risk/risk-treatment-plan.md) | 47 actions; 4 open |
| NH-SOA-001 | [Statement of Applicability](03-risk/statement-of-applicability.csv) | 93 controls assessed |

### Policies

| ID | Policy | Primary controls |
|---|---|---|
| NH-POL-002 | [Access control](04-policies/access-control-policy.md) | A.5.15–A.5.18, A.8.2–A.8.5, A.8.18 |
| NH-POL-003 | [Acceptable use and information handling](04-policies/acceptable-use-and-information-handling-policy.md) | A.5.10–A.5.14, A.7.10, A.8.12 |
| NH-POL-004 | [Human resources security](04-policies/human-resources-security-policy.md) | A.6.1–A.6.8 |
| NH-POL-005 | [Physical and environmental security](04-policies/physical-and-environmental-security-policy.md) | A.7.1–A.7.14 |
| NH-POL-006 | [Incident management](04-policies/incident-management-policy.md) | A.5.24–A.5.28, A.6.8 |
| NH-POL-007 | [Supplier security](04-policies/supplier-security-policy.md) | A.5.19–A.5.23, A.8.30 |
| NH-POL-008 | [Backup, continuity and recovery](04-policies/backup-continuity-and-recovery-policy.md) | A.8.13, A.8.14, A.5.29, A.5.30 |
| NH-POL-009 | [Secure development and change management](04-policies/secure-development-and-change-management-policy.md) | A.8.25–A.8.33, A.5.3, A.5.8 |
| NH-POL-010 | [Vulnerability and configuration management](04-policies/vulnerability-and-configuration-management-policy.md) | A.8.8, A.8.9, A.8.19–A.8.23 |
| NH-POL-011 | [Data retention and privacy](04-policies/data-retention-and-privacy-policy.md) | A.5.31, A.5.33, A.5.34, A.8.10 |
| NH-POL-012 | [Logging and monitoring](04-policies/logging-and-monitoring-policy.md) | A.8.15–A.8.17 |
| NH-POL-013 | [Remote working and mobile devices](04-policies/remote-working-and-mobile-device-policy.md) | A.6.7, A.7.9, A.8.1, A.8.23 |
| NH-POL-014 | [Cryptography and key management](04-policies/cryptography-and-key-management-policy.md) | A.8.24 |

### Operation and evidence

| ID | Document | Status |
|---|---|---|
| NH-PRC-001 | [Onboarding and offboarding procedure](05-operation/onboarding-offboarding-procedure.md) | Approved |
| NH-PRC-002 | [Access review procedure](05-operation/access-review-procedure.md) | Approved |
| NH-PRC-002-R1 | [Q1 2027 access review record](05-operation/access-review-record-q1-2027.md) | Completed 31 March 2027 |
| NH-PRC-003 | [Incident response plan](05-operation/incident-response-plan.md) | Approved |
| NH-PRC-004 | [Backup restore test record](05-operation/backup-restore-test-record.md) | Completed 14 March 2027 |
| NH-PRC-005 | [Business continuity and disaster recovery plan](05-operation/business-continuity-and-disaster-recovery-plan.md) | Approved |
| NH-PRC-006 | [Security awareness programme](05-operation/security-awareness-programme.md) | Active |
| NH-PRC-008 | [Data subject request procedure](05-operation/data-subject-request-procedure.md) | Approved |
| NH-SEC-001 | [Penetration test summary](05-operation/penetration-test-summary.md) | High finding remediated |
| NH-REG-003 | [Supplier register](05-operation/supplier-register.csv) | 12 suppliers |
| NH-EVD-001 | [Evidence index](05-operation/evidence-index.md) | Maintained |

### Performance and improvement

| ID | Document | Status |
|---|---|---|
| NH-KPI-001 | [KPIs and metrics](06-performance/kpis-and-metrics.md) | Q1 2027 results |
| NH-AUD-001 | [Internal audit plan](06-performance/internal-audit-plan.md) | Completed |
| NH-AUD-002 | [Internal audit report](06-performance/internal-audit-report.md) | 3 minor NCs, 4 observations, 2 OFIs |
| NH-MR-001 | [Management review minutes](06-performance/management-review-minutes.md) | Approved 29 April 2027 |
| NH-NC-001 | [Nonconformity and corrective action log](07-improvement/nonconformity-and-corrective-actions.csv) | 1 closed, 8 open |

### Diagrams

- [Platform architecture](diagrams/architecture.mmd)
- [ISMS process map](diagrams/isms-process.mmd)

## 5. How to read this project

1. Start with the [fact base](00-company-fact-base.md) to understand the company and its
   22 baseline gaps.
2. Read the [scope](01-context/isms-scope.md) and [risk methodology](03-risk/risk-methodology.md)
   to understand what is covered and how risk is scored.
3. Open the [risk register](03-risk/risk-register.csv) and [Statement of Applicability](03-risk/statement-of-applicability.csv)
   side by side. Each risk maps to Annex A controls; each control justifies its
   applicability and status.
4. Review the [treatment plan](03-risk/risk-treatment-plan.md) to see how risks were
   reduced, who owns each action, and what evidence exists.
5. Read the [internal audit report](06-performance/internal-audit-report.md) and
   [management review](06-performance/management-review-minutes.md) to see how the ISMS
   performs under scrutiny.

## 6. Traceability conventions

| ID | Meaning |
|---|---|
| G-01 to G-22 | Baseline gaps in the fact base |
| A-CL, A-AP, A-EP, A-NW | Cloud, application, endpoint, and network assets |
| D-01 to D-14 | Information assets and data sets |
| S-01 to S-12 | Suppliers |
| R-01 to R-26 | Risks in the risk register |
| T-xx | Treatment actions |
| NC-xx, OBS-xx, OFI-xx | Audit findings and improvement actions |
| EVD-xx | Evidence index entries |

Every risk names the gap, asset, and controls it relates to. Every audit finding names
the requirement, risk, correction, root cause, and corrective action. The evidence index
tells an auditor where to verify each claim.

## 7. Limitations

- All evidence is simulated. No real system, customer, or regulator was involved.
- Legal positions, including PDPL transfer requirements, are summaries requiring
  confirmation by Egyptian counsel.
- The internal audit is a simulation of an independent audit, not an actual certification
  audit.
- The project reflects a point-in-time ISMS. In a real engagement, the register, SoA,
  and evidence would continue to change weekly.
