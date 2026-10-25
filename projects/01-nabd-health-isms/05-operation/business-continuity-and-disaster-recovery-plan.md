# Business Continuity and Disaster Recovery Plan

| Field | Value |
|---|---|
| Document ID | NH-PRC-005 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 20 March 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This plan is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. Contact
> details are fictional placeholders.

## 1. Purpose

This plan defines how Nabd Health continues critical services and recovers from a
disruption affecting the platform, data, office, or key people. It supports A.5.29 and
A.5.30 and the 99.9 percent availability commitment in customer contracts.

It is activated when normal incident response cannot restore service within the
containment target, or when the incident commander expects the RTO to be exceeded.

## 2. Scope

Covers the Nabd Platform (web, API, patient app, Admin Panel), production data, support
operations, customer communication, and the Cairo office. Marketing activities and
Pixelwave premises are out of scope.

## 3. Business impact analysis

| Priority | Business process | Dependency | Impact of loss | RTO | RPO |
|---|---|---|---|---|---|
| 1 | Patient access to records and bookings | AWS, RDS, S3, API | Patient care disruption; clinic operations stop; contractual breach | 8 hours | 1 hour |
| 1 | Telemedicine sessions | API, VideoBridge, SMSGate | Missed consultations; patient harm risk | 8 hours | 1 hour |
| 1 | Admin Panel support | AWS, SSO | Clinics cannot be supported; record access lost | 8 hours | 1 hour |
| 1 | Payment processing | PayNile, API | Revenue loss; clinic billing disrupted | 8 hours | 1 hour |
| 2 | Customer support and communication | Email, Slack, Freshdesk | Delayed response; reputational impact | 12 hours | 4 hours |
| 2 | Security monitoring and incident response | CloudWatch, GuardDuty, logs | Reduced detection and evidence | 8 hours | 1 hour |
| 3 | Reporting and analytics | Data warehouse, RDS replica | Management visibility reduced | 72 hours | 24 hours |
| 3 | HR, finance, and admin | Google Workspace, payroll | Internal delay | 72 hours | 24 hours |

The analysis is reviewed annually and after a major change. It assumes clinics can
continue limited paper-based operations for a short period but cannot access Nabd
records.

## 4. Activation

| Level | Trigger | Authority | Action |
|---|---|---|---|
| Alert | Elevated risk, regional AWS issue, supplier warning | DevOps Lead | Monitor, prepare, inform CTO |
| Partial activation | Single service degraded but workaround exists | CTO | Activate recovery for affected service |
| Full activation | Platform unavailable beyond 2 hours, data loss, or regional outage | CEO on CTO advice | Crisis team, customer communication, DR invocation |
| Disaster | Prolonged regional failure or office loss | CEO | Alternate region, remote operations, insurer and customer notification |

The CEO declares a disaster. In the CEO's absence, the COO declares and informs the CEO
as soon as possible.

## 5. Crisis team

| Role | Person | Responsibility |
|---|---|---|
| Crisis lead | CEO | Overall decision, external communication approval |
| Technical recovery | CTO | Recovery strategy and execution |
| Operations | DevOps Lead | Runbooks, restoration, infrastructure |
| Customer communication | COO | Status updates, account managers, support continuity |
| Patient communication | CPO | Patient impact and notices |
| Legal, privacy, insurance | CFO | Regulator, contracts, insurer, counsel |
| People | HR Manager | Staff safety, remote arrangements, contact tracking |
| Scribe | ISMS Manager | Decision log, timeline, evidence |

The team meets in the incident bridge and uses the decision log in Appendix B. A deputy
is named for every role.

## 6. Recovery strategies

### 6.1 Regional AWS failure

1. Declare the incident and assess the affected region.
2. Use cross-region backups and infrastructure-as-code to rebuild in the secondary
   region. The target is restoration of Priority 1 services within 8 hours.
3. Update DNS and certificates; validate data integrity and tenant isolation.
4. Communicate with customers and monitor for errors.
5. Record gaps and update the plan; a full secondary-region active-active design is not
   currently funded.

### 6.2 Data corruption or ransomware

1. Isolate affected systems and preserve evidence.
2. Identify a clean backup before the corruption or encryption time.
3. Restore into an isolated environment and validate integrity.
4. Rotate credentials and secrets before reconnecting.
5. Follow the incident notification matrix.

### 6.3 Loss of Cairo office

1. Staff work remotely; the office is not required for platform operation.
2. Recover fobs, devices, and documents when safe.
3. Use the landlord and building management for access and damage assessment.
4. If devices are lost, issue replacements and enforce encryption and MDM.
5. Communicate with staff and customers as needed.

### 6.4 Supplier outage

| Supplier | Impact | Workaround |
|---|---|---|
| AWS | Platform unavailable | Regional recovery; AWS support |
| GitHub | Cannot deploy; source still local | Use mirror and local builds; read-only mode |
| Google Workspace | Email and SSO affected | Break-glass admin accounts; alternate contact |
| SMSGate | OTP and reminders fail | Secondary SMS provider; patient app fallback |
| VideoBridge | Telemedicine unavailable | Reschedule or use approved alternate; notify patients |
| PayNile | Payments unavailable | Queue transactions; communicate to clinics |
| Freshdesk | Support ticketing unavailable | Shared inbox and incident bridge |

### 6.5 Key person unavailability

Runbooks and cross-training allow a second platform engineer and the CTO to perform
recovery. Break-glass credentials are sealed and stored with the CTO and CEO.

## 7. Recovery sequence

1. Safety and people.
2. Contain the incident and preserve evidence.
3. Restore identity and access.
4. Restore database and patient files.
5. Restore application and Admin Panel.
6. Validate integrity, tenant isolation, and security controls.
7. Restore integrations (SMS, video, payments).
8. Resume support and customer communication.
9. Monitor and confirm stability.
10. Post-incident review and plan update.

## 8. Alternate operations

- Support can operate from home using managed devices and the VPN.
- Customer communication can use the account management contact list and Google
  Workspace from any location.
- Clinics are advised to use their own downtime procedure for patient care and to record
  transactions for later entry.
- Paper records created during an outage must be handled as Highly Confidential and
  entered into the platform as soon as it is available.

## 9. Security during disruption

Controls must not be bypassed for convenience. If a control cannot operate:

- document the compensating control and its owner;
- limit access to the minimum people;
- log actions manually where system logging is unavailable;
- restore the control as soon as possible;
- review the period after recovery for unauthorized activity.

Emergency access uses break-glass accounts with MFA, CEO notification, and a review
within one business day.

## 10. Communications

| Audience | Owner | Channel | Frequency |
|---|---|---|---|
| Crisis team | Scribe | Incident bridge and email | Continuous |
| Staff | HR Manager | Email and Slack | At activation and daily |
| Customers | COO | Account managers and status email | Within 2 hours, then every 4 hours |
| Patients | CPO | App and email where needed | As required |
| Regulator | CFO | Formal channel | As required |
| Insurer | CFO | Claims channel | Within policy timeframe |
| Board | CEO | Call and written summary | Within 24 hours for a disaster |

## 11. Return to normal

The crisis lead declares recovery when:

- Priority 1 services are stable for 24 hours;
- data integrity and security controls are validated;
- customer communication confirms acceptable service;
- outstanding risks are documented and accepted;
- the post-incident review is scheduled.

A recovery report is issued within 10 business days and actions are tracked in NH-NC-001.

## 12. Testing and maintenance

| Activity | Frequency | Owner |
|---|---|---|
| Backup restore test | Quarterly | DevOps Lead |
| Tabletop exercise | Every six months | CTO |
| Full DR exercise | Annually, where feasible | CTO |
| Contact list review | Quarterly | ISMS Manager |
| BIA and plan review | Annually and after major change | CTO |

## 13. Appendix A: Decision log

| Time | Decision | Made by | Rationale | Follow-up |
|---|---|---|---|---|
| | | | | |

## 14. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 20 March 2027 | Initial BCP/DR plan after tabletop exercise | CTO |
