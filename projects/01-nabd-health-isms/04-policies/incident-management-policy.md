# Incident Management Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-006 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 5 February 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines how Nabd Health prepares for, detects, assesses, responds to, and
learns from information security incidents. It implements Annex A controls A.5.24 to
A.5.28 and A.6.8, and supports contractual breach notification obligations.

## 2. Scope

Applies to all staff, contractors, suppliers, and systems within the ISMS scope. It
covers security incidents, suspected data breaches, availability incidents with a
security cause, and losses of devices or credentials.

## 3. Definitions

| Term | Definition |
|---|---|
| Event | An observable occurrence in a system or service |
| Security event | An event that may indicate a security incident |
| Incident | A confirmed or suspected event that affects confidentiality, integrity, or availability, or violates policy |
| Data breach | An incident leading to accidental or unlawful destruction, loss, alteration, or unauthorized disclosure of personal data |
| Major incident | Severity 1 or 2 under the matrix in Section 5 |

## 4. Reporting

All staff and contractors must report suspected incidents immediately through:

- the incident mailbox `security@nabdhealth.example` (simulated);
- the Slack channel `#security-incidents`;
- the reporting button in email;
- direct contact with the CTO or DevOps Lead for urgent matters.

Reporting must include what happened, when, which systems or data are involved, and
what has been done so far. Staff must not attempt to investigate or remediate an
incident themselves unless instructed. Good-faith reporting is protected.

Suppliers must notify Nabd of an incident affecting Nabd data without undue delay and
within the period defined in the contract.

## 5. Severity

| Severity | Criteria | Response | Notification |
|---|---|---|---|
| 1 Critical | Confirmed patient data breach at scale; platform unavailable over 2 hours; ransomware; production compromise | Immediate; incident team and CEO | CEO, board, affected customers, regulator via counsel, insurer |
| 2 High | Suspected patient data exposure; account compromise; Admin Panel abuse; outage 30 minutes to 2 hours | Within 1 hour | CTO, CEO, affected customer account manager |
| 3 Medium | Limited exposure; lost encrypted device; malware contained; degraded service | Within 4 business hours | CTO, ISMS Manager |
| 4 Low | Policy violation or near miss with no data impact | Within 1 business day | ISMS Manager |

Severity may be raised as understanding develops. When in doubt, treat the incident as
more severe until triage is complete.

## 6. Response phases

1. **Prepare**: maintain the plan, contacts, templates, access, and evidence tools;
   exercise at least twice a year.
2. **Detect and report**: receive alerts and reports, log them, and assign an incident
   owner.
3. **Assess**: confirm whether an incident exists, determine severity, affected data,
   systems, and customers, and preserve evidence.
4. **Contain**: revoke access, isolate systems, block indicators, and prevent further
   harm while preserving business continuity.
5. **Eradicate**: remove the cause, patch, rebuild, and verify that the threat is gone.
6. **Recover**: restore services, validate integrity, and monitor for recurrence.
7. **Notify**: inform executives, customers, regulators, insurers, and law enforcement
   as required and within contractual or legal deadlines.
8. **Learn**: hold a post-incident review within ten business days, record lessons, and
   create corrective actions.

The operational detail is in NH-PRC-003.

## 7. Notification

| Audience | Trigger | Owner | Timing |
|---|---|---|---|
| CEO and executive team | Severity 1 or 2 | Incident owner | Immediately |
| Board | Severity 1; material regulatory or customer impact | CEO | Within 24 hours |
| Affected hospital customers | Confirmed or suspected breach of their data | COO | Within 72 hours where contracted |
| Data protection authority | Reportable personal data breach | CFO with counsel | As required by PDPL |
| Patients | High risk to their rights or data | CPO with counsel | Without undue delay where required |
| Cyber insurer | Incident likely to exceed deductible or trigger cover | CFO | Per policy |
| Law enforcement | Criminal activity or legal requirement | CFO with counsel | As advised by counsel |

No external notification may be issued without CEO approval and legal review, except
where a legal deadline requires immediate action.

## 8. Evidence

Evidence must be collected lawfully, documented, and preserved. The incident owner
records:

- time, source, and description of the event;
- systems, accounts, and data involved;
- actions taken and by whom;
- copies of logs, screenshots, and communications;
- chain of custody for devices or media.

Evidence is stored in a restricted incident folder and retained according to NH-POL-011.

## 9. Roles

| Role | Responsibility |
|---|---|
| CEO | Declares major incidents, approves external notifications, informs the board |
| CTO | Incident commander for technical incidents; owns the response process |
| DevOps Lead | Technical containment, recovery, and evidence preservation |
| ISMS Manager | Maintains the register, coordinates reviews and corrective actions |
| CFO | Regulatory and contractual notification, insurer, legal counsel |
| COO | Customer communication and service continuity |
| CPO | Patient impact assessment and patient communication |
| HR Manager | Employee-related incidents and disciplinary process |
| All staff | Report promptly and follow instructions |

## 10. Testing and improvement

The incident response plan is exercised at least twice a year, including one scenario
involving patient data and one involving availability. Exercises are recorded, lessons
are tracked to closure, and the plan is updated.

## 11. Related documents

- NH-POL-001 Information Security Policy
- NH-POL-007 Supplier Security Policy
- NH-POL-011 Data Retention and Privacy Policy
- NH-POL-012 Logging and Monitoring Policy
- NH-PRC-003 Incident Response Plan
- NH-PRC-005 Business Continuity and Disaster Recovery Plan
- NH-NC-001 Nonconformity and Corrective Action Log

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 5 February 2027 | Initial incident management policy | ISMS Lead Implementer |
