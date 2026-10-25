# Access Review Procedure

| Field | Value |
|---|---|
| Document ID | NH-PRC-002 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 20 February 2027 |
| Owner | Ahmed Rizk, DevOps Lead |
| Approved by | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This procedure is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This procedure defines how Nabd Health reviews access to ensure it remains appropriate,
least-privileged, and attributable. It supports A.5.15, A.5.18, A.8.2, and A.8.3.

## 2. Scope and frequency

| Access type | Frequency | Reviewer | Approver |
|---|---|---|---|
| AWS privileged and production access | Quarterly | DevOps Lead | CTO |
| Admin Panel and patient record access | Quarterly | Head of Support | CTO |
| GitHub organization and repository admin | Quarterly | Engineering Manager | CTO |
| Google Workspace admin roles | Quarterly | IT Support Officer | CTO |
| SaaS tools with confidential data | Every six months | System owner | CTO |
| All other systems | Annually | Line managers | Asset owner |
| Supplier and contractor access | At each contract review and on change | Sponsoring manager | CTO |

## 3. Inputs

- HR active staff and contractor list.
- Identity provider user list and group membership.
- AWS IAM Identity Center users, permission sets, and service accounts.
- GitHub organization members, teams, and outside collaborators.
- Admin Panel user list and roles.
- SaaS administrator and user lists.
- Joiners, movers, and leavers since the last review.
- Privileged access and break-glass log.

## 4. Process

1. **Prepare**: the reviewer exports the access list and compares it with the HR list.
2. **Identify exceptions**: accounts without an active person, excessive roles, shared
   accounts, dormant accounts, and access without an approved request.
3. **Decide**: for each account, record one of: retain, reduce, remove, or investigate.
4. **Act**: changes are made within five working days; security concerns are actioned
   immediately.
5. **Confirm**: the reviewer records completion, decisions, and evidence.
6. **Report**: metrics and exceptions go to the CTO and the Security and Risk Committee.

## 5. Review criteria

- The person is active in HR records and has a current contract.
- The role matches the person's current job.
- Access is necessary for the role and approved by the asset owner.
- Privileged access is limited to named administrators.
- No shared accounts or shared credentials exist.
- Service accounts have an owner, a purpose, and no interactive use.
- Dormant accounts (no login for 60 days) are disabled unless justified.
- Contractor access is limited to the agreed scope and end date.

## 6. Evidence

The review record includes:

- date and scope of the review;
- reviewer and approver;
- source data and comparison method;
- number of accounts reviewed;
- decisions and actions, with owners and due dates;
- confirmation that actions were completed;
- any exceptions and their approval.

Evidence is stored in the access review folder and referenced in NH-EVD-001.

## 7. Metrics

| Metric | Target |
|---|---|
| Reviews completed on schedule | 100 percent |
| Accounts removed within 5 working days | 100 percent |
| Dormant accounts without justification | 0 |
| Shared accounts found | 0 |
| Contractor accounts beyond end date | 0 |

## 8. Related documents

- NH-POL-002 Access Control Policy
- NH-PRC-001 Onboarding and Offboarding Procedure
- NH-POL-012 Logging and Monitoring Policy
- NH-REG-003 Supplier Register

## 9. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 20 February 2027 | Initial access review procedure | DevOps Lead |
