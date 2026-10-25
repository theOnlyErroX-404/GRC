# KPIs and Metrics

| Field | Value |
|---|---|
| Document ID | NH-KPI-001 |
| Version | 1.2 |
| Status | Maintained |
| Simulation date | 30 April 2027 |
| Owner | ISMS Manager |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This report is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This document defines the information security objectives and the metrics used to
measure them (clauses 6.2 and 9.1). Results are reviewed monthly by the CTO and quarterly
by the Security and Risk Committee and management review.

## 2. Objectives for 2027

1. Reduce Critical and High risks to Medium or lower.
2. Achieve 100 percent MFA coverage for staff, contractors, and administrators.
3. Demonstrate recovery capability against the approved RTO and RPO.
4. Achieve ISO/IEC 27001 certification readiness by June 2027.
5. Reduce phishing susceptibility and increase incident reporting.
6. Close audit nonconformities within their agreed dates.

## 3. Metric definitions and results

| KPI | Metric | Definition | Target | Frequency | Owner | Q1 2027 | Q2 to date | Trend |
|---|---|---|---|---|---|---|---|---|
| KPI-01 | Critical and High risks above appetite | Count of risks rated High or Critical after treatment | 0 | Monthly | CTO | 0 (from 20) | 0 | Stable |
| KPI-02 | Treatment actions on time | Completed by due date / total due | 90 percent | Monthly | ISMS Manager | 91 percent (43/47) | 100 percent | Improving |
| KPI-03 | MFA coverage | Users with MFA / total users | 100 percent | Monthly | IT Support Officer | 100 percent | 100 percent | Stable |
| KPI-04 | Privileged access review completion | Reviews completed on schedule | 100 percent | Quarterly | DevOps Lead | 100 percent | 100 percent | Stable |
| KPI-05 | Leaver access removed on time | Leavers removed on or before last day / total | 100 percent | Monthly | HR Manager | 83 percent (5/6) | 100 percent | Improving |
| KPI-06 | Critical vulnerability SLA | Critical vulnerabilities fixed within 7 days / total | 100 percent | Monthly | DevOps Lead | 100 percent | 100 percent | Stable |
| KPI-07 | High vulnerability SLA | High vulnerabilities fixed within 30 days / total | 95 percent | Monthly | DevOps Lead | 94 percent | 96 percent | Improving |
| KPI-08 | Endpoint encryption | Managed endpoints encrypted / total managed | 100 percent | Monthly | IT Support Officer | 100 percent | 100 percent | Stable |
| KPI-09 | Backup restore test success | Successful restore tests / planned | 100 percent | Quarterly | DevOps Lead | 100 percent (1/1) | 1 planned | On track |
| KPI-10 | Security incidents | Confirmed incidents by severity | Track and trend | Monthly | CTO | 3 (all Low) | 1 (Low) | Stable |
| KPI-11 | Incident reporting rate | Reports per 100 staff per month | Above 2 | Monthly | ISMS Manager | 2.4 | 2.6 | Improving |
| KPI-12 | Phishing click rate | Clicks / recipients per simulation | Below 5 percent | Monthly | HR Manager | 3.4 percent | 3.1 percent | Improving |
| KPI-13 | Awareness completion | Completed mandatory modules / assigned | 100 percent | Quarterly | HR Manager | 100 percent | 100 percent | Stable |
| KPI-14 | Tier 1 supplier assessments current | Current assessments / tier 1 suppliers | 100 percent | Quarterly | CFO | 71 percent (5/7) | 86 percent (6/7) | Improving |
| KPI-15 | Platform availability | Uptime against 99.9 percent contract | At least 99.9 percent | Monthly | CTO | 99.93 percent | 99.95 percent | Stable |
| KPI-16 | Audit nonconformities closed on time | Closed by due date / total | 100 percent | Per audit | ISMS Manager | 0/3 open | 1/3 closed | Improving |
| KPI-17 | Data subject requests on time | Completed within legal period / total | 100 percent | Monthly | CFO | 100 percent (2/2) | 100 percent (1/1) | Stable |
| KPI-18 | Security log retention compliance | Required sources retained / required | 100 percent | Quarterly | DevOps Lead | 100 percent | 100 percent | Stable |

## 4. Exceptions and analysis

- **KPI-05 (leaver access):** one Freshdesk account remained active after termination
  (NC-02). The account was disabled on 17 April 2027. The cause was a gap in the SaaS
  checklist, which was updated.
- **KPI-07 (high vulnerabilities):** one high finding exceeded 30 days because it required
  an upstream dependency update. A compensating control was applied and the fix shipped
  on 9 April 2027.
- **KPI-14 (supplier assessments):** VideoBridge and Pixelwave assessments were pending.
  Pixelwave was completed on 20 April 2027; VideoBridge is due 30 April 2027.
- **KPI-16 (audit nonconformities):** NC-01 and NC-03 remain open with due dates in May
  2027. NC-02 closed on 28 April 2027 after verification.

## 5. Reporting

| Report | Audience | Frequency | Owner |
|---|---|---|---|
| Security dashboard | CTO and ISMS Manager | Monthly | ISMS Manager |
| Risk and KPI report | Security and Risk Committee | Quarterly | CTO |
| Management review pack | CEO and executives | Annual and as needed | ISMS Manager |
| Board summary | Board | Quarterly | CEO |

Metrics are trended over at least four quarters. Targets are reviewed annually and when
the risk profile changes.

## 6. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 31 January 2027 | Initial KPI set | ISMS Manager |
| 1.1 | 31 March 2027 | Added supplier, DSR, and audit metrics | ISMS Manager |
| 1.2 | 30 April 2027 | Q1 results and Q2 to date | ISMS Manager |
