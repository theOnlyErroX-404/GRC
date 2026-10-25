# Access Review Record — Q1 2027

| Field | Value |
|---|---|
| Document ID | NH-PRC-002-R1 |
| Review period | Q1 2027 |
| Review date | 31 March 2027 |
| Reviewers | Ahmed Rizk (DevOps Lead); Nour El-Din Abbas (Head of Support); Mariam Khalil (HR Manager) |
| Approver | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This record is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Scope

| System | Accounts reviewed | Reviewer |
|---|---|---|
| Google Workspace | 63 (60 staff, 3 contractors) plus 4 shared mailboxes | IT Support Officer |
| AWS IAM Identity Center | 18 human users; 2 service roles | DevOps Lead |
| GitHub organization | 39 members and outside collaborators | Engineering Manager |
| Admin Panel | 19 accounts | Head of Support |
| Freshdesk, Slack, Jira, HubSpot, Figma, Sentry | 63 users across tools | IT Support Officer |
| Supplier and contractor access | 3 Pixelwave developers; 2 supplier support accounts | CTO |

## 2. Method

The reviewer exported the user list from each system, compared it with the HR active
list, checked role assignments against the role matrix, and identified dormant,
excessive, shared, or orphaned accounts. Decisions were recorded as retain, reduce,
remove, or investigate.

## 3. Results

| Result | Count | Action |
|---|---|---|
| Accounts reviewed | 63 staff and contractors; 19 Admin Panel; 18 AWS; 39 GitHub | — |
| Accounts removed | 3 | 2 former Pixelwave contractors (GitHub); 1 dormant Slack account |
| Accounts disabled pending investigation | 1 | Freshdesk account for a leaver (NC-02) |
| Roles reduced | 4 | Admin Panel administrators reduced from 7 to 4; 2 AWS permission sets narrowed |
| Dormant accounts disabled | 2 | No login for more than 60 days, no business justification |
| Shared accounts found | 0 | Shared Google Sheet credentials removed in February 2027 |
| Contractor accounts beyond end date | 0 | Pixelwave roster confirmed with the supplier |
| Exceptions approved | 1 | Read-only production access retained for one engineer on call, time-limited to 30 June 2027 |

## 4. Findings

### 4.1 Former contractor access

Two GitHub accounts belonging to former Pixelwave contractors were still members of the
organization. Both were removed on 15 January 2027, before this review. The removal is
evidenced in the GitHub audit log.

### 4.2 Leaver SaaS account (NC-02)

One Freshdesk agent account remained active for 19 days after the user's last working
day. The account was identified in the audit sample and disabled on 17 April 2027. The
offboarding checklist was updated to include Freshdesk and all SaaS tools. This is
tracked as NC-02 and was verified closed on 28 April 2027.

### 4.3 Admin Panel privilege

Seven of nineteen Admin Panel accounts had administrator rights, more than required. The
number was reduced to four: the Head of Support, the support team lead, and two operations
managers. Record access is now time-bound and logged.

### 4.4 AWS access

Sixteen legacy IAM users were reduced to two service roles. Human access uses IAM
Identity Center with permission sets. Two long-unused access keys were deleted, and the
remaining service keys have rotation dates.

## 5. Evidence

- Exported user lists with review annotations (access review folder).
- HR active list as at 31 March 2027.
- GitHub audit log entries for the two removals.
- Admin Panel role matrix and change record.
- AWS Identity Center configuration export.
- Freshdesk account disable log.

## 6. Conclusion

Access is materially improved from the baseline. No shared accounts remain, privileged
access is limited, and contractor access matches the supplier roster. One leaver account
was missed in a SaaS tool, which is a minor nonconformity and is being corrected.

## 7. Sign-off

| Role | Name | Date |
|---|---|---|
| Reviewer | Ahmed Rizk | 31 March 2027 |
| Reviewer | Nour El-Din Abbas | 31 March 2027 |
| HR confirmation | Mariam Khalil | 31 March 2027 |
| Approver | Omar Nasser | 1 April 2027 |
