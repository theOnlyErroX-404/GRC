# Onboarding and Offboarding Procedure

| Field | Value |
|---|---|
| Document ID | NH-PRC-001 |
| Version | 1.1 |
| Status | Approved |
| Simulation date | 15 February 2027 |
| Owner | Mariam Khalil, HR Manager |
| Approved by | Dina Mostafa, COO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This procedure is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This procedure ensures that access, assets, and security obligations are handled
consistently when people join, move, or leave Nabd Health. It supports A.5.11, A.5.18,
A.6.1, A.6.2, A.6.5, and A.7.9.

## 2. Scope

Applies to employees, interns, and contractors, including Pixelwave developers. Supplier
personnel who are not individually onboarded are managed under NH-POL-007.

## 3. Roles

| Role | Responsibility |
|---|---|
| HR Manager | Starts the process, confirms screening and contracts, notifies IT |
| Line manager | Defines role and access, completes onboarding, conducts exit |
| IT Support Officer | Creates accounts, issues devices, removes access |
| DevOps Lead | Provisioning and removal for AWS, GitHub, and production |
| Asset owner | Approves access to their system |
| ISMS Manager | Audits completion and reports exceptions |

## 4. Onboarding

### 4.1 Before the start date

| Step | Owner | Timing | Record |
|---|---|---|---|
| Signed contract and NDA | HR Manager | Before start | HR file |
| Screening completed (identity, references, role-specific checks) | HR Manager | Before start | Screening record |
| Role and access request submitted | Line manager | At least 3 working days before start | Service desk ticket |
| Device prepared and encrypted | IT Support Officer | Before start | Asset register |
| Accounts created with least privilege | IT Support Officer / DevOps Lead | On start, after HR confirmation | Access record |
| Policy acknowledgement and awareness assigned | HR Manager | Day 1 | LMS record |

No access is granted before HR confirms the signed contract and completed screening.
A documented exception requires CTO approval.

### 4.2 Day one

1. HR delivers the security briefing and collects policy acknowledgement.
2. IT issues the device, MFA token or passkey, and password manager access.
3. The line manager explains role-specific data handling and reporting channels.
4. The new starter completes the first awareness module within five working days.
5. Access is verified against the approved request; excess access is removed.

### 4.3 First 30 days

- Complete all mandatory awareness modules.
- Confirm understanding of incident reporting and acceptable use.
- Line manager reviews access and confirms it is appropriate.
- HR records completion.

## 5. Access change (mover)

1. HR or the line manager submits a change request with the new role and effective date.
2. The new asset owner approves new access.
3. IT adds new access and removes access no longer required within five working days.
4. A confirmation is recorded and the access review includes the change.

## 6. Offboarding

### 6.1 Planned departure

| Step | Owner | Timing | Record |
|---|---|---|---|
| Notify IT and DevOps of last working day | HR Manager | At least 5 working days before | Offboarding ticket |
| Prepare access removal list | IT Support Officer | 2 working days before | Checklist |
| Knowledge transfer and handover | Line manager | Before last day | Handover note |
| Exit interview and continuing obligations | HR Manager | Before last day | Exit record |
| Remove access (Google, AWS, GitHub, SaaS, Admin Panel, VPN) | IT / DevOps | On or before last day | Removal confirmation |
| Recover laptop, fobs, and documents | IT / Office Manager | Last day | Asset return record |
| Remote wipe personal device profile | IT Support Officer | Last day | MDM record |
| Confirm completion to ISMS Manager | HR Manager | Within 2 working days | Closure record |

### 6.2 Urgent departure

For dismissal or a security concern:

1. HR or the CTO authorizes immediate suspension.
2. IT disables identity and sessions within one hour.
3. Devices are recovered or wiped remotely.
4. Access removal is confirmed the same day.
5. The ISMS Manager is informed and the event is considered for the risk register.

### 6.3 Contractor departure

The sponsoring manager confirms the end date to HR and IT. The same removal and asset
return steps apply. Pixelwave confirms that its developer no longer holds Nabd code or
data on personal devices.

## 7. Records and audit

Records are retained per NH-POL-011. The ISMS Manager samples at least six joiners,
movers, and leavers per quarter and reports exceptions. A leaver account found active
after the last working day is a security incident and a nonconformity.

## 8. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-004 Human Resources Security Policy
- NH-PRC-002 Access Review Procedure
- NH-REG-001 Asset Register

## 9. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 5 February 2027 | Initial procedure | HR Manager |
| 1.1 | 15 February 2027 | Added urgent departure timing and contractor steps | HR Manager |
