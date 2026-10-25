# Access Control Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-002 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 22 January 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | January 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines how access to Nabd Health information, systems, and facilities is
granted, used, reviewed, and removed. It implements Annex A controls A.5.15, A.5.16,
A.5.17, A.5.18, A.8.2, A.8.3, A.8.4, A.8.5, and A.8.18.

## 2. Scope

Applies to all employees, contractors, suppliers, and support accounts that access the
Nabd Platform, AWS, GitHub, Google Workspace, the Admin Panel, or any system holding
Nabd information.

## 3. Principles

1. **Least privilege**: users receive the minimum access required for their role.
2. **Need to know**: access to patient data requires a documented support or clinical
   purpose.
3. **Unique identity**: every action must be attributable to one person. Shared
   accounts and shared credentials are prohibited.
4. **Default deny**: access is granted explicitly and expires when no longer needed.
5. **Tenant isolation**: clinic data is isolated by clinic ID and enforced in
   application code and access reviews.

## 4. Account lifecycle

| Stage | Requirement | Owner |
|---|---|---|
| Request | Access request in the service desk with role, systems, justification, and duration; approval by the line manager and asset owner | Line manager |
| Provisioning | IT creates a unique account and assigns the approved role; no access beyond the request | IT Support Officer |
| Change | Role changes require a new approval; excess access is removed within five working days | IT Support Officer |
| Review | Quarterly for privileged, Admin Panel, and production data access; annually for other systems | Asset owners |
| Removal | HR notifies IT before the last working day; access removed on or before the last day; confirmation recorded | HR Manager / IT Support Officer |
| Emergency removal | CTO or HR Manager can request immediate suspension at any time | CTO / HR Manager |

Contractors follow the same lifecycle. Pixelwave contractors are sponsored by the CTO
and limited to the mobile repositories and staging environment they require.

## 5. Authentication

1. MFA is mandatory for Google Workspace, AWS, GitHub, the Admin Panel, and all SaaS
   tools that support it.
2. Administrators must use phishing-resistant MFA (passkeys or hardware security keys)
   for Google Workspace and AWS.
3. Passwords must be at least 14 characters, unique per service, and checked against a
   breached-password source. A company password manager is provided and must be used.
4. Passwords, API keys, and private keys must never be shared, pasted into tickets, or
   stored in documents or spreadsheets.
5. Service accounts use short-lived credentials or rotated secrets stored in AWS Secrets
   Manager; long-lived access keys require CTO approval and rotation every 90 days.
6. Patient accounts use phone OTP with rate limiting, device binding, and session
   revocation. OTP codes are valid for 10 minutes and single use.
7. Authentication events are logged and monitored under NH-POL-012.

## 6. Privileged access

1. Privileged access is granted only to named administrators with a business need.
2. Administrators use a separate account for administrative activity where the platform
   supports it.
3. AWS human access uses IAM Identity Center permission sets. The AWS root user is used
   only for break-glass tasks, with MFA and CEO notification.
4. SSH access to the bastion uses per-person certificates or keys. Shared key pairs are
   prohibited.
5. Privileged sessions are logged. Break-glass use is reviewed within one business day.
6. Privileged access is reviewed quarterly and after any administrator leaves.
7. No utility program capable of overriding system or application controls may be
   installed without CTO approval.

## 7. Remote and third-party access

1. Remote access to production requires the company VPN, MFA, and a managed device.
2. The Admin Panel is reachable only through the VPN or an approved IP allow-list.
3. Supplier access is time-bound, scoped, sponsored by a Nabd owner, and recorded in the
   supplier register.
4. Third-party access is removed at the end of the engagement and reviewed at each
   supplier review.

## 8. Access to source code and production data

1. GitHub access requires organization 2FA, team-based permissions, and branch
   protection. Repository admin rights are limited to the CTO and DevOps Lead.
2. Production database access is read-only by default, time-bound, and requires a
   ticket. Direct write access requires CTO approval and is logged.
3. Patient record access through the Admin Panel requires a support case reference and a
   reason; access is logged and reviewed weekly.
4. Exports of patient data require Head of Support approval and are logged.

## 9. Monitoring and compliance

Access is monitored through authentication logs, access reviews, and quarterly sampling.
Repeated failed logins, impossible-travel events, and unusual export volumes generate
alerts. Deliberate misuse may lead to disciplinary action or contract termination.

## 10. Exceptions

Exceptions must be requested in writing, approved by the CTO, recorded with an expiry
date, and reviewed at management review. Exceptions involving patient data require a
compensating control and CFO awareness.

## 11. Related documents

- NH-POL-001 Information Security Policy
- NH-POL-012 Logging and Monitoring Policy
- NH-POL-013 Remote Working and Mobile Device Policy
- NH-PRC-001 Onboarding and Offboarding Procedure
- NH-PRC-002 Access Review Procedure
- NH-REG-001 Asset Register
- NH-REG-003 Supplier Register

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 22 January 2027 | Initial access control policy | ISMS Lead Implementer |
