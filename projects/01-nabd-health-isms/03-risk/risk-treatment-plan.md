# Risk Treatment Plan

| Field | Value |
|---|---|
| Document ID | NH-PLN-001 |
| Version | 1.2 |
| Status | Approved |
| Simulation date | 15 April 2027 |
| Owner | ISMS Lead Implementer |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This document is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This plan records how Nabd Health treats the risks in the risk register (NH-REG-002),
who is accountable, when actions are due, and the evidence required to show that
treatment is operating. It implements ISO/IEC 27001:2022 clause 6.1.3 and is reviewed at
least quarterly by the Security and Risk Committee.

## 2. Approach

- Treatment is prioritized by risk rating: Critical risks were addressed first, then
  High, then Medium.
- Actions are grouped into six workstreams so that one control change can reduce several
  related risks.
- Every action has a named owner, a due date, and defined evidence. An action is not
  closed because a document exists; it is closed when the control has operated and the
  evidence is retained.
- Residual risk is assessed after at least one full operating cycle. Where the residual
  remains above appetite, additional treatment or formal acceptance is required.
- The risk appetite and acceptance authority are defined in NH-RISK-001.

## 3. Summary

| Rating | Inherent | Residual at 15 April 2027 | Target |
|---|---|---|---|
| Critical (17–25) | 6 | 0 | 0 |
| High (10–16) | 14 | 0 | 0 |
| Medium (5–9) | 6 | 22 | All accepted or treated |
| Low (1–4) | 0 | 4 | Monitor |
| **Total** | **26** | **26** | |

All 26 risks now have a residual score of 9 or lower. Four risks remain in treatment at
the date of this plan: R-02 (leaver access), R-12 (staging masking), R-15 (supplier
reviews), and R-22 (PDPL programme). The related corrective actions are tracked in
NH-NC-001 and were raised by the internal audit.

## 4. Treatment workstreams

### 4.1 Identity, access, and authentication

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-01 | R-01 | Enforce MFA for all Google Workspace, AWS, GitHub, and Admin Panel users; require phishing-resistant methods for administrators | CTO | 2027-02-28 | Complete | MFA enforcement report; 60 of 60 staff and 3 of 3 contractors enrolled |
| T-02 | R-01 | Correct the cyber insurance declaration and notify the insurer of the MFA remediation date | CFO | 2027-01-31 | Complete | Insurer acknowledgement letter |
| T-03 | R-02 | Publish and operate the joiner-mover-leaver procedure with an HR-triggered deadline and IT confirmation | HR Manager | 2027-02-15 | Complete | Procedure NH-PRC-001; 6 leaver records sampled |
| T-04 | R-02 | Remove former Pixelwave contractor accounts and complete a full access review of GitHub, AWS, Google, and SaaS tools | DevOps Lead | 2027-03-15 | In progress | 2 GitHub accounts removed; Freshdesk leaver account outstanding (NC-02) |
| T-05 | R-10 | Deploy a company password manager and remove credentials from the shared Google Sheet | DevOps Lead | 2027-02-28 | Complete | 1Password tenant; sheet archived and access removed |
| T-06 | R-10 | Replace shared bastion key pairs with per-person SSH certificates; rotate remaining keys | DevOps Lead | 2027-03-31 | Complete | Certificate authority configuration; key rotation record |
| T-07 | R-10 | Move AWS human access to IAM Identity Center with permission sets and session duration limits | CTO | 2027-03-31 | Complete | Identity Center configuration export; 16 legacy IAM users reduced to 2 service roles |
| T-08 | R-19 | Restrict Admin Panel access to the corporate VPN or approved IP allow-list and enforce MFA at the edge | CTO | 2027-03-15 | Complete | WAF and ALB configuration; access test record |
| T-09 | R-19 | Add rate limiting, bot protection, and alerting for failed Admin Panel logins | DevOps Lead | 2027-03-15 | Complete | WAF rule export; alert test |
| T-10 | R-26 | Add OTP rate limits, device binding, session revocation, and anomaly alerts for patient accounts | CPO | 2027-03-31 | Complete | Product release note; test evidence |

### 4.2 Patient data protection and privacy

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-11 | R-04 | Redesign Admin Panel roles to least privilege and introduce time-bound access to patient records with a reason code | Head of Support | 2027-03-15 | Complete | Role matrix; access request records |
| T-12 | R-04 | Log patient record views, searches, and exports, and review anomalous activity weekly | DevOps Lead | 2027-03-31 | Complete | Audit log schema; 12 weekly review records |
| T-13 | R-12 | Build an automated masking pipeline for every staging refresh, covering all patient and employee data | DevOps Lead | 2027-03-31 | In progress | 11 of 14 tables masked; 3 tables outstanding (NC-01) |
| T-14 | R-12 | Restrict staging access to the engineers who require it and remove the monthly production copy default | CTO | 2027-02-28 | Complete | IAM group membership; pipeline configuration |
| T-15 | R-16 | Approve a retention schedule by data type and implement automated deletion with legal hold | CPO | 2027-03-31 | Complete | Retention schedule; deletion job logs |
| T-16 | R-21 | Publish support data-handling rules, redaction guidance, and ticket templates; add DLP rules for email and Slack | Head of Support | 2027-03-15 | Complete | Guidance; DLP configuration; quarterly QA sample |
| T-17 | R-22 | Complete records of processing, a DPIA for the platform, and a cross-border transfer assessment for Bahrain | CFO | 2027-04-30 | In progress | RoPA v1; DPIA draft; transfer assessment in legal review |
| T-18 | R-22 | Appoint a DPO and publish the data subject request procedure | CFO | 2027-03-31 | Complete | Appointment letter; procedure NH-PRC-008 |
| T-19 | R-22 | Execute DPAs with SMSGate, VideoBridge, PayNile, and other personal-data suppliers | CFO | 2027-03-31 | Complete | Signed DPAs in contract repository |

### 4.3 Resilience and continuity

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-20 | R-03 | Define RPO (1 hour) and RTO (8 hours) for the platform and obtain business approval | CTO | 2027-01-31 | Complete | Approved objectives in NH-PRC-005 |
| T-21 | R-03 | Enable cross-region backup copies for RDS and S3 and test restoration of both | DevOps Lead | 2027-03-31 | Complete | Restore test record NH-PRC-004; 14 March 2027 |
| T-22 | R-03 | Write and exercise the business continuity and disaster recovery plan | CTO | 2027-03-31 | Complete | Plan NH-PRC-005; tabletop exercise minutes |
| T-23 | R-18 | Replace routine admin bypass with an emergency change process requiring CTO approval and a post-implementation review | Engineering Manager | 2027-02-28 | Complete | Change policy NH-POL-009; 4 emergency changes sampled |
| T-24 | R-18 | Automate rollback testing in the deployment pipeline and record results | Engineering Manager | 2027-03-31 | Complete | Pipeline configuration; 6 rollback records |
| T-25 | R-23 | Monitor SLOs, review capacity monthly, and load test before seasonal peaks | CTO | 2027-03-31 | Complete | Capacity review; load test report |
| T-26 | R-25 | Cross-train a second platform engineer and document AWS, CI/CD, and bastion runbooks | CTO | 2027-03-31 | Complete | Training record; runbook index |

### 4.4 Detection, response, and secure engineering

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-27 | R-06 | Deliver quarterly awareness training and monthly phishing simulations with role-specific content | COO | 2027-03-31 | Complete | LMS completion 100 percent; simulation results |
| T-28 | R-06 | Enforce DMARC reject, SPF, and DKIM; add an external reporting mailbox and button | IT Support Officer | 2027-02-28 | Complete | DNS records; mailbox |
| T-29 | R-08 | Centralize security logs with 12-month retention and route GuardDuty, CloudTrail, and WAF alerts to an on-call channel | DevOps Lead | 2027-03-15 | Complete | Log archive configuration; alert routing test |
| T-30 | R-08 | Publish a triage runbook and record weekly alert reviews | DevOps Lead | 2027-03-31 | Complete | Runbook; 10 weekly review records |
| T-31 | R-09 | Implement dependency, container, and infrastructure scanning in CI with severity-based patch SLAs | CTO | 2027-03-15 | Complete | Scanner configuration; SLA in NH-POL-010 |
| T-32 | R-09 | Commission the first external penetration test and remediate high findings | CTO | 2027-03-31 | Complete | Penetration test report; remediation tracker |
| T-33 | R-11 | Publish the incident response plan, severity matrix, on-call rota, and notification templates | CTO | 2027-02-28 | Complete | Plan NH-PRC-003; contact list |
| T-34 | R-11 | Run a ransomware tabletop and a customer notification exercise | CTO | 2027-03-31 | Complete | Exercise report; lessons log |
| T-35 | R-24 | Pin dependencies, sign images, scan pull requests, and replace long-lived CI secrets with OIDC | CTO | 2027-03-31 | Complete | GitHub configuration; secret scanning report |

### 4.5 Assets, endpoints, and physical security

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-36 | R-07 | Complete the asset inventory and enrol all laptops and desktops in MDM with encryption enforcement | IT Support Officer | 2027-03-15 | Complete | Asset register; MDM compliance report |
| T-37 | R-07 | Enforce screen lock, disk encryption, and endpoint protection baselines on macOS and Windows | IT Support Officer | 2027-03-15 | Complete | MDM profiles; compliance report |
| T-38 | R-17 | Set minimum security requirements for contractor and personal devices and require MDM for company email | IT Support Officer | 2027-03-31 | Complete | Contractor agreement schedule; MDM enrolment |
| T-39 | R-14 | Reconcile fobs with the staff list, lock the network cupboard, and enforce visitor escort and sign-in | Office Manager | 2027-02-28 | Complete | Fob reconciliation report; visitor log audit |
| T-40 | R-14 | Implement clear desk and clear screen checks with quarterly spot checks | Office Manager | 2027-03-31 | Complete | Checklist; 2 spot-check records |
| T-41 | R-20 | Introduce a certified wipe and disposal register for all devices leaving Nabd | IT Support Officer | 2027-03-31 | Complete | Disposal register; 9 wipe certificates |

### 4.6 Suppliers and ISMS governance

| Action ID | Risk | Action | Owner | Due | Status | Evidence |
|---|---|---|---|---|---|---|
| T-42 | R-05 | Revise the Pixelwave agreement with confidentiality, security, audit, and data protection terms | CTO | 2027-02-28 | Complete | Signed agreement; security schedule |
| T-43 | R-15 | Build the supplier register and tier suppliers by data access and criticality | CFO | 2027-02-15 | Complete | Supplier register NH-REG-003 |
| T-44 | R-15 | Complete due diligence for tier 1 suppliers, including AWS, Google, GitHub, SMSGate, VideoBridge, PayNile, and Pixelwave | CFO | 2027-04-30 | In progress | 5 of 7 assessments complete at 15 April 2027; Pixelwave completed 20 April 2027 |
| T-45 | R-15 | Add security and data protection clauses to all new and renewed supplier contracts | CFO | 2027-03-31 | Complete | Contract template; 4 signed amendments |
| T-46 | R-13 | Implement the ISMS document set, risk assessment, SoA, internal audit, and management review | ISMS Manager | 2027-04-30 | Complete | Document index; audit report; management review minutes |
| T-47 | R-13 | Conduct a certification readiness review against ISO/IEC 27001:2022 | ISMS Manager | 2027-05-15 | Complete | Readiness report |

## 5. Residual risk acceptance

All residual risks are within the appetite defined in NH-RISK-001. Critical and High
inherent risks were reduced to Medium or Low. Acceptance is recorded below; the full
scoring detail is in NH-REG-002.

| Risk | Inherent | Residual | Residual rating | Accepted by | Expiry |
|---|---|---|---|---|---|
| R-01 | 16 High | 6 | Medium | CTO | 2027-10-15 |
| R-02 | 16 High | 6 | Medium | CEO | 2027-07-15 |
| R-03 | 15 High | 8 | Medium | CTO | 2027-10-15 |
| R-04 | 20 Critical | 8 | Medium | CEO | 2027-07-15 |
| R-05 | 16 High | 6 | Medium | CTO | 2027-10-15 |
| R-06 | 16 High | 6 | Medium | COO | 2027-10-15 |
| R-07 | 16 High | 8 | Medium | CTO | 2027-10-15 |
| R-08 | 16 High | 6 | Medium | CTO | 2027-07-15 |
| R-09 | 20 Critical | 8 | Medium | CEO | 2027-07-15 |
| R-10 | 20 Critical | 8 | Medium | CEO | 2027-07-15 |
| R-11 | 16 High | 6 | Medium | CTO | 2027-07-15 |
| R-12 | 20 Critical | 6 | Medium | CEO | 2027-06-30 |
| R-13 | 16 High | 3 | Low | CEO | 2028-04-15 |
| R-14 | 9 Medium | 4 | Low | Office Manager | 2028-04-15 |
| R-15 | 16 High | 9 | Medium | CFO | 2027-10-15 |
| R-16 | 16 High | 6 | Medium | CPO | 2027-10-15 |
| R-17 | 12 High | 6 | Medium | CTO | 2027-10-15 |
| R-18 | 16 High | 6 | Medium | CTO | 2027-10-15 |
| R-19 | 20 Critical | 8 | Medium | CEO | 2027-07-15 |
| R-20 | 9 Medium | 3 | Low | IT Support Officer | 2028-04-15 |
| R-21 | 16 High | 6 | Medium | Head of Support | 2027-10-15 |
| R-22 | 20 Critical | 8 | Medium | CEO | 2027-07-15 |
| R-23 | 12 High | 6 | Medium | CTO | 2027-10-15 |
| R-24 | 15 High | 8 | Medium | CTO | 2027-07-15 |
| R-25 | 12 High | 6 | Medium | CTO | 2027-10-15 |
| R-26 | 12 High | 6 | Medium | CPO | 2027-10-15 |

Residual scores for R-02, R-12, R-15, and R-22 are provisional until their outstanding
actions are complete. They are re-assessed at the next Security and Risk Committee.

## 6. Overdue and escalated actions

At 15 April 2027, no action is more than 30 days overdue. The four open actions (T-04,
T-13, T-17, T-44) are tracked weekly by the ISMS Manager and are reported in the
management review of 29 April 2027. If T-13 is not complete by 30 April 2027, the staging
environment will be switched to synthetic data only, which removes the exposure
regardless of the masking backlog.

## 7. Effectiveness measurement

| Measure | Target | Actual at 15 April 2027 |
|---|---|---|
| Treatment actions complete on time | 90 percent | 43 of 47 (91 percent) |
| Critical risks reduced to Medium or lower | 100 percent | 6 of 6 |
| High risks reduced to Medium or lower | 100 percent | 14 of 14 |
| Restore tests completed | 4 per year | 1 (14 March 2027) |
| Phishing simulation failure rate | Below 5 percent | 3.4 percent (March 2027) |
| MFA coverage | 100 percent | 100 percent |
| Critical vulnerabilities open beyond SLA | 0 | 0 |
| Supplier assessments complete (tier 1) | 100 percent | 5 of 7 |

## 8. Review and revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 15 January 2027 | Initial treatment plan after risk workshop | ISMS Lead Implementer |
| 1.1 | 28 February 2027 | Progress update; four actions re-baselined | ISMS Manager |
| 1.2 | 15 April 2027 | Residual risk assessment and audit alignment | ISMS Manager |

Next review: 29 April 2027 (management review), then quarterly.
