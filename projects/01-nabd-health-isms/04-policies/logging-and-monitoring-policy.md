# Logging and Monitoring Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-012 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 26 February 2027 |
| Owner | Ahmed Rizk, DevOps Lead |
| Approved by | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines what Nabd Health logs, how long logs are retained, how they are
protected, and how monitoring alerts are reviewed and acted on. It implements Annex A
controls A.8.15, A.8.16, and A.8.17.

## 2. Scope

Applies to AWS accounts, applications, the Admin Panel, identity providers, endpoints,
network services, SaaS tools, and security tooling within the ISMS scope.

## 3. Logging requirements

| Source | Events logged | Retention | Owner |
|---|---|---|---|
| AWS CloudTrail | All management events and selected data events | 12 months in S3 | DevOps Lead |
| AWS GuardDuty | Findings and severity | 12 months | DevOps Lead |
| VPC and WAF | Flow logs, blocked requests, rate-limit events | 90 days | DevOps Lead |
| Application and API | Authentication, authorization failures, errors, admin actions, data exports | 90 days hot, 12 months archive | Engineering Manager |
| Admin Panel | Logins, patient record views, searches, exports, permission changes | 12 months | Head of Support |
| Google Workspace | Logins, admin changes, MFA changes, sharing changes | 12 months | IT Support Officer |
| GitHub | Push, permission, secret scanning, branch protection changes | 12 months | CTO |
| Endpoints | Malware, encryption, patch, and MDM compliance events | 90 days | IT Support Officer |
| Database | Privileged access, schema changes, failed logins | 90 days | DevOps Lead |

Logs must include, where applicable, timestamp, user or service identity, source IP,
action, target, outcome, and correlation ID. Patient record views and exports are always
logged with the support case or user reason.

## 4. Log protection

1. Logs are stored in a dedicated, access-restricted account or bucket with versioning
   and object lock where supported.
2. Logs are encrypted at rest and in transit.
3. Application and support roles cannot delete or modify security logs.
4. Access to logs is limited to the DevOps Lead, CTO, ISMS Manager, and auditors.
5. Log integrity controls (validation, hashing, or immutable storage) are enabled where
   available.
6. Time synchronization uses AWS time services; endpoint time is enforced by MDM.

## 5. Monitoring and alerting

The following alerts are routed to the on-call channel and reviewed:

- GuardDuty medium, high, and critical findings;
- root or break-glass account use;
- MFA changes for administrators;
- repeated failed logins or impossible-travel events;
- public S3 bucket or security group changes;
- Admin Panel access from unusual locations or bulk patient record views;
- WAF blocks above threshold and signs of credential stuffing;
- backup failures, restore failures, and abnormal database growth;
- production deployment failures and SLO breaches;
- new GitHub organization owners or branch protection changes.

Alerts have a documented owner, severity, and runbook. Alerts that are not actionable
must be tuned or removed to prevent fatigue.

## 6. Review and triage

| Activity | Frequency | Owner |
|---|---|---|
| Review of open alerts and triage decisions | Daily (business days) | DevOps Lead |
| Weekly security alert summary | Weekly | DevOps Lead |
| Admin Panel access and export review | Weekly | Head of Support |
| Privileged access and root use review | Monthly | CTO |
| Log retention and integrity check | Quarterly | DevOps Lead |
| Monitoring effectiveness review | Quarterly | Security and Risk Committee |

Triage decisions are recorded in the security operations log with the alert, assessment,
action, and closure reason. Suspected incidents are escalated under NH-PRC-003.

## 7. Retention and disposal

Logs are retained for the periods in Section 3 and then deleted, unless a legal hold or
investigation requires preservation. Deletion is automated where possible and recorded.
Logs may contain personal data; access is restricted and retention is minimized.

## 8. Roles

| Role | Responsibility |
|---|---|
| CTO | Owns monitoring strategy and resources |
| DevOps Lead | Operates logging, alerting, and triage |
| Engineering Manager | Ensures application logging meets requirements |
| Head of Support | Reviews patient record access and exports |
| IT Support Officer | Maintains identity and endpoint logs |
| ISMS Manager | Reviews evidence and reports monitoring performance |

## 9. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-006 Incident Management Policy
- NH-POL-010 Vulnerability and Configuration Management Policy
- NH-PRC-003 Incident Response Plan
- NH-KPI-001 KPIs and Metrics

## 10. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 26 February 2027 | Initial logging and monitoring policy | DevOps Lead |
