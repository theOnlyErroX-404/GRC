# Secure Development and Change Management Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-009 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 19 February 2027 |
| Owner | Sara Lotfy, Engineering Manager |
| Approved by | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines how security is built into the development lifecycle and how changes
reach production safely. It implements Annex A controls A.8.25 to A.8.33, A.5.3, A.5.8,
A.5.21, A.5.32, and A.8.4.

## 2. Scope

Applies to all application, infrastructure, mobile, and configuration changes to the
Nabd Platform, including work performed by Pixelwave contractors.

## 3. Secure development lifecycle

| Phase | Security requirement |
|---|---|
| Requirements | Identify confidentiality, integrity, availability, privacy, and abuse cases; trigger DPIA for personal-data changes |
| Design | Threat model high-risk changes; apply least privilege, tenant isolation, encryption, and secure defaults |
| Build | Follow secure coding standards; no secrets in code; peer review required |
| Test | SAST, dependency and container scanning, DAST for staging, and security acceptance criteria |
| Release | Change approval, automated rollback, signed images, and release notes |
| Operate | Monitoring, vulnerability management, and post-release review |

Security requirements are part of the definition of done. A change that cannot meet them
requires a documented risk acceptance approved by the CTO.

## 4. Source code and branches

1. Source code is held in the `nabd-health` GitHub organization.
2. Organization-level 2FA is required. Access is team-based and reviewed quarterly.
3. `main` is protected: at least one approving review, passing build, and no direct
   pushes.
4. Repository admin bypass is restricted to the CTO and DevOps Lead and must be recorded
   as an emergency change.
5. Secrets are never committed. Secret scanning and push protection are enabled.
6. Dependencies are pinned and reviewed; new dependencies require a licence and
   maintenance check.
7. Code from contractors is reviewed by a Nabd engineer before merge.

## 5. Security testing

| Test | Frequency | Owner |
|---|---|---|
| SAST | Every pull request | Engineering |
| Dependency and licence scan | Every build and daily | Engineering |
| Container image scan | Every build | DevOps |
| Secret scanning | Continuous | Engineering |
| DAST | Weekly on staging and before major releases | Engineering |
| Penetration test | Annually and after major architecture change | CTO |
| Threat model | For high-risk features | Engineering Manager |

High and critical findings must be fixed before release. Medium findings require a
tracked action. Accepted findings require CTO approval with a compensating control.

## 6. Environments and test data

1. Production and non-production use separate AWS accounts.
2. Development and staging share `nabd-nonprod`; access is restricted to engineering and
   selected support staff.
3. Staging must use synthetic or masked data. Production copies require CTO approval,
   masking, and a time limit.
4. Test data must not be copied to personal devices or public services.
5. Production credentials are never used in development or testing.

## 7. Change management

### 7.1 Normal changes

- Raised in Jira with a description, risk assessment, test evidence, and rollback plan.
- Reviewed by a second engineer and approved by the Engineering Manager for significant
  changes.
- Deployed through the pipeline with automated tests and monitoring.
- Release notes record the change, approver, and deployment time.

### 7.2 Emergency changes

An emergency change is permitted only to restore service, address a critical
vulnerability, or prevent imminent harm.

1. The CTO or delegate approves verbally or in writing.
2. The change is recorded in Jira within one business day.
3. A post-implementation review is completed within five business days.
4. Repeated emergency changes trigger a root-cause review.

Direct pushes to `main` are prohibited except under this process.

### 7.3 Rollback

Every production change has a rollback or roll-forward plan. Rollback is tested for
database and infrastructure changes. Failed deployments are reverted before further
changes are attempted.

## 8. Separation of duties

- The person who writes a change cannot be the only approver.
- Production access is separate from development access where practical.
- The CTO and DevOps Lead cannot both be absent without a named deputy.

## 9. Outsourced development

Pixelwave developers work on mobile repositories under Nabd review. They must not:

- access production data or infrastructure;
- approve their own changes;
- introduce dependencies without review;
- store code or credentials outside the Nabd GitHub organization.

Their agreement includes confidentiality, IP assignment, and security obligations.

## 10. Artificial intelligence coding tools

AI coding assistants may be used only with approved tools and no patient data,
credentials, or proprietary source code unless the tool is contractually approved for
that purpose. Generated code is reviewed like any other contribution and must not
introduce licence or security risk.

## 11. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-010 Vulnerability and Configuration Management Policy
- NH-POL-014 Cryptography and Key Management Policy
- NH-PRC-003 Incident Response Plan
- NH-PRC-004 Backup Restore Test Record
- diagrams/architecture.mmd

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 19 February 2027 | Initial secure development and change management policy | Engineering Manager |
