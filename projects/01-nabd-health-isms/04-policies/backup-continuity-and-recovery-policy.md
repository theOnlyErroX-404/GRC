# Backup, Continuity and Recovery Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-008 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 12 February 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines backup, restoration, business continuity, and disaster recovery
requirements for the Nabd Platform. It implements Annex A controls A.8.13, A.8.14,
A.5.29, and A.5.30, and supports the 99.9 percent availability commitments in customer
contracts.

## 2. Scope

Applies to production data, configuration, source code, and supporting services in
`nabd-prod` and `nabd-nonprod`, and to the business functions required to operate and
support the platform.

## 3. Recovery objectives

| Service or data | RPO | RTO | Notes |
|---|---|---|---|
| Nabd Platform (web, API, patient app) | 1 hour | 8 hours | Priority 1 |
| RDS PostgreSQL production | 1 hour | 4 hours | Multi-AZ and point-in-time recovery |
| S3 patient files | 1 hour | 8 hours | Versioning and cross-region copy |
| Admin Panel | 1 hour | 8 hours | Priority 1 |
| Support and customer communication | 4 hours | 12 hours | Priority 2 |
| Reporting and analytics | 24 hours | 72 hours | Priority 3 |
| Source code and infrastructure code | 24 hours | 8 hours | GitHub plus local mirrors |

RPO and RTO are approved by the CEO and reviewed annually or after a major architecture
change. They are communicated to customers only through approved contract language.

## 4. Backup requirements

| Asset | Method | Frequency | Retention | Location |
|---|---|---|---|---|
| RDS PostgreSQL | Automated snapshots and point-in-time recovery | Continuous; daily snapshot | 7 days operational, 12 monthly | me-south-1 plus cross-region copy |
| S3 patient files | Versioning and replication | Continuous | 12 months of versions | me-south-1 plus secondary region |
| Terraform state | Versioned bucket | On every apply | 12 months | me-south-1 |
| GitHub repositories | Native GitHub plus encrypted mirror | Daily | 90 days | Secondary account or region |
| Google Workspace | Google Vault and export | Daily | Per retention schedule | Google |
| Configuration and runbooks | Git and document repository | On change | 12 months | GitHub and Drive |
| Secrets | AWS Secrets Manager with recovery window | On change | 30 days | AWS |

Backups must be encrypted at rest and in transit, access-restricted, and protected from
deletion by the account or identity that holds the source data. At least one copy of
critical data must be outside the primary region.

## 5. Restoration testing

1. A restore test is performed at least quarterly, and after any significant change to
   backup configuration.
2. Each test covers at least one database restore, one S3 object restore, and
   verification of application functionality against restored data.
3. Results are recorded in NH-PRC-004 with date, scope, duration, RPO/RTO achieved,
   issues, and actions.
4. Failed or partial tests create a corrective action and are reported to the Security
   and Risk Committee.
5. Restores into non-production use masked or synthetic data wherever possible.

## 6. Business continuity and disaster recovery

The business continuity and disaster recovery plan (NH-PRC-005) defines:

- activation criteria and decision authority;
- the crisis team and contact list;
- alternate operating arrangements for support and customer communication;
- recovery sequence for critical services;
- communication with customers, regulators, and staff;
- security controls during degraded operations;
- return to normal operation and post-incident review.

The plan is exercised at least annually through a tabletop exercise and, where feasible,
a technical recovery test.

## 7. Monitoring and assurance

- Backup jobs are monitored, and failures alert the DevOps Lead.
- Backup success rates and restore test results are reported in NH-KPI-001.
- Retention and immutability settings are reviewed quarterly.
- Access to backups is limited to the DevOps Lead, CTO, and break-glass accounts.
- A restore test that cannot meet RTO is treated as a High risk until resolved.

## 8. Roles

| Role | Responsibility |
|---|---|
| CEO | Approves RPO/RTO and declares a disaster |
| CTO | Owns continuity and recovery; activates the DR plan |
| DevOps Lead | Operates backups, performs restores, maintains runbooks |
| COO | Maintains customer communication and alternate support arrangements |
| CFO | Coordinates legal, regulatory, and insurance communication |
| ISMS Manager | Tracks tests, exercises, and corrective actions |

## 9. Related documents

- NH-POL-006 Incident Management Policy
- NH-POL-012 Logging and Monitoring Policy
- NH-PRC-003 Incident Response Plan
- NH-PRC-004 Backup Restore Test Record
- NH-PRC-005 Business Continuity and Disaster Recovery Plan
- NH-REG-001 Asset Register

## 10. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 12 February 2027 | Initial policy including approved RPO and RTO | ISMS Lead Implementer |
