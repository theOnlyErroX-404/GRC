# Evidence Index

| Field | Value |
|---|---|
| Document ID | NH-EVD-001 |
| Version | 1.2 |
| Status | Maintained |
| Simulation date | 23 April 2027 |
| Owner | ISMS Manager |
| Approved by | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This index is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. Evidence
> references point to simulated records.

## 1. Purpose

This index tells an auditor where to find objective evidence that controls are designed
and operating. It links each evidence item to the relevant clause, Annex A control, or
risk, and names the owner and retention period.

## 2. Index

| Evidence ID | Clause or control | Evidence | Location | Owner | Date | Retention |
|---|---|---|---|---|---|---|
| EVD-01 | 4.1, 4.2 | Context and issues register; interested-party register | `01-context/context-and-issues.md`; `01-context/interested-parties.md` | ISMS Manager | 2026-11-20 | 3 years |
| EVD-02 | 4.3 | Approved ISMS scope | `01-context/isms-scope.md` | CEO | 2026-11-27 | 3 years |
| EVD-03 | 5.1, 5.2, 5.3 | Information security policy approval; roles and RACI | `02-leadership/information-security-policy.md`; `02-leadership/roles-and-responsibilities.md` | CEO | 2026-12-15 | 3 years |
| EVD-04 | 6.1.2 | Risk methodology approval | `03-risk/risk-methodology.md` | CEO | 2027-01-08 | 3 years |
| EVD-05 | 6.1.2, A.5.9 | Asset register with owners and criticality | `03-risk/asset-register.csv` | CTO | 2027-04-15 | 3 years |
| EVD-06 | 6.1.2, 6.1.3 | Risk register and scoring | `03-risk/risk-register.csv` | CTO | 2027-04-15 | 3 years |
| EVD-07 | 6.1.3 | Risk treatment plan and residual acceptance | `03-risk/risk-treatment-plan.md` | CEO | 2027-04-15 | 3 years |
| EVD-08 | 6.1.3, 6.2 | Statement of Applicability with 93 controls assessed | `03-risk/statement-of-applicability.csv` | CTO | 2027-04-15 | 3 years |
| EVD-09 | A.5.15, A.5.16, A.5.17, A.8.5 | MFA enforcement report for Google, AWS, GitHub, and Admin Panel | Access review folder | DevOps Lead | 2027-03-31 | 3 years |
| EVD-10 | A.5.18, A.8.2 | Q1 2027 access review record and privileged access decisions | `05-operation/access-review-record-q1-2027.md`; access review folder | DevOps Lead | 2027-03-31 | 3 years |
| EVD-11 | A.6.5, A.5.11 | Offboarding sample of 6 leavers with access removal and asset return | HR and service desk | HR Manager | 2027-04-10 | 3 years |
| EVD-12 | A.8.2, A.5.16 | IAM Identity Center configuration and legacy IAM user reduction | AWS configuration export | DevOps Lead | 2027-03-31 | 3 years |
| EVD-13 | A.8.15, A.8.3 | Admin Panel view, search, and export logging configuration and weekly reviews | Security operations folder | Head of Support | 2027-04-15 | 12 months |
| EVD-14 | A.8.11, A.8.33 | Staging masking status: 11 of 14 tables complete; NC-01 and remediation plan | Engineering folder | DevOps Lead | 2027-04-15 | 3 years |
| EVD-15 | A.8.13, A.5.30 | Backup restore test BRT-2027-Q1, including RTO and RPO results | `05-operation/backup-restore-test-record.md` | DevOps Lead | 2027-03-14 | 3 years |
| EVD-16 | A.5.29, A.5.30 | BCP/DR plan and tabletop exercise minutes | `05-operation/business-continuity-and-disaster-recovery-plan.md`; exercise folder | CTO | 2027-03-20 | 3 years |
| EVD-17 | A.5.24 to A.5.27 | Incident response plan, exercise report, and incident register | `05-operation/incident-response-plan.md`; incident folder | CTO | 2027-03-31 | 3 years |
| EVD-18 | A.6.3 | Awareness completion records and phishing simulation results | Learning management system; `05-operation/security-awareness-programme.md` | HR Manager | 2027-03-31 | 3 years |
| EVD-19 | A.8.8, A.8.29 | Vulnerability scan reports, patch SLA report, penetration test summary and retest | `05-operation/penetration-test-summary.md`; engineering and security folders | CTO | 2027-03-31 | 3 years |
| EVD-20 | A.5.19 to A.5.23 | Supplier register, due diligence records, DPAs, and contract amendments | `05-operation/supplier-register.csv`; contract repository | CFO | 2027-04-15 | 6 years for contracts |
| EVD-21 | A.5.31, A.5.34, A.8.10 | Records of processing, DPIA, cross-border assessment, DSR procedure and register | Privacy folder; `04-policies/data-retention-and-privacy-policy.md` | CFO | 2027-04-30 | 6 years |
| EVD-22 | A.5.35, 9.2 | Simulated internal audit plan, report, findings, and working papers | `06-performance/internal-audit-plan.md`; `06-performance/internal-audit-report.md` | ISMS Manager | 2027-04-23 | 6 years |
| EVD-23 | 9.3 | Management review minutes and action log | `06-performance/management-review-minutes.md` | CEO | 2027-04-29 | 3 years |
| EVD-24 | 10.1, 10.2 | Nonconformity and corrective action log with evidence of closure | `07-improvement/nonconformity-and-corrective-actions.csv` | ISMS Manager | 2027-04-30 | 3 years |
| EVD-25 | 6.2, 9.1 | KPI report with targets and actuals | `06-performance/kpis-and-metrics.md` | ISMS Manager | 2027-04-15 | 3 years |
| EVD-26 | A.7.2 to A.7.7 | Fob reconciliation, visitor log audit, clear desk checks | Office folder | Office Manager | 2027-03-31 | 3 years |
| EVD-27 | A.8.1, A.7.9 | MDM compliance report: encryption, screen lock, patch status | MDM console export | IT Support Officer | 2027-03-31 | 3 years |
| EVD-28 | A.8.32 | Change records, emergency change approvals, rollback test records | Jira and CI/CD records | Engineering Manager | 2027-03-31 | 3 years |
| EVD-29 | A.6.6, A.5.20 | Signed Pixelwave agreement with security schedule; supplier template | Contract repository | CFO | 2027-02-28 | 6 years |
| EVD-30 | A.5.37 | Procedure set for onboarding, access review, incidents, backup, continuity, awareness, DSR | `05-operation/` | ISMS Manager | 2027-04-30 | 3 years |
| EVD-31 | A.8.24 | Cryptography and key management policy; KMS and certificate configuration | `04-policies/cryptography-and-key-management-policy.md`; AWS configuration | CTO | 2027-02-26 | 3 years |
| EVD-32 | A.8.16 | Weekly security alert review records and triage decisions | Security operations folder | DevOps Lead | 2027-04-15 | 12 months |

## 3. Evidence handling rules

1. Evidence must be authentic, dated, and attributable to an owner.
2. Screenshots include the system, date, and user context where possible.
3. Exports are stored read-only and access-restricted.
4. Personal data in evidence is minimized or redacted where it is not needed.
5. Evidence is retained for the period in the index and longer under legal hold.
6. The ISMS Manager samples evidence quarterly to confirm it remains available and
   current.

## 4. Gaps

| Gap | Impact | Action |
|---|---|---|
| Cross-region restore not yet demonstrated | R-03 treatment incomplete | Test scheduled 2027-06-15 |
| Supplier assessments 6 of 7 tier 1 complete | R-15 treatment in progress | Complete VideoBridge assessment by 2027-04-30 |
| DPIA and transfer assessment in legal review | R-22 treatment in progress | Complete by 2027-04-30 |
| Endpoint EDR not deployed | A.8.7 partial | Rollout Q3 2027 |

## 5. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 28 February 2027 | Initial evidence index | ISMS Manager |
| 1.1 | 31 March 2027 | Added access, backup, and awareness evidence | ISMS Manager |
| 1.2 | 23 April 2027 | Aligned to internal audit findings and gaps | ISMS Manager |
