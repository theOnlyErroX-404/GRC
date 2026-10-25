# Incident Response Plan

| Field | Value |
|---|---|
| Document ID | NH-PRC-003 |
| Version | 1.1 |
| Status | Approved |
| Simulation date | 5 March 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This plan is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. Contact
> details are fictional placeholders.

## 1. Purpose and authority

This plan operationalizes NH-POL-006. It gives the incident team a consistent way to
detect, assess, contain, eradicate, recover from, and learn from security incidents, and
to meet the 72-hour customer notification obligation in five hospital contracts.

The CTO is the incident commander for technical incidents. The CEO declares a Severity 1
incident and approves external notifications. In their absence, the COO and Engineering
Manager act as deputies.

## 2. Scope

Covers incidents affecting the confidentiality, integrity, or availability of Nabd
information or services, including supplier incidents, lost devices, insider misuse, and
regulatory breaches.

## 3. Contact list

| Role | Name | Contact | Alternate |
|---|---|---|---|
| Incident commander | Omar Nasser, CTO | cto@nabdhealth.example; +20 100 000 0001 | Sara Lotfy, Engineering Manager |
| Executive sponsor | Karim Salah, CEO | ceo@nabdhealth.example; +20 100 000 0002 | Dina Mostafa, COO |
| Technical lead | Ahmed Rizk, DevOps Lead | devops@nabdhealth.example; +20 100 000 0003 | Platform engineer on call |
| Support and customer communication | Nour El-Din Abbas, Head of Support | support-lead@nabdhealth.example; +20 100 000 0004 | Support team lead |
| Privacy and legal | Heba Youssef, CFO | cfo@nabdhealth.example; +20 100 000 0005 | External counsel |
| Product and patient impact | Layla Hamdy, CPO | cpo@nabdhealth.example; +20 100 000 0006 | Product manager |
| HR | Mariam Khalil, HR Manager | hr@nabdhealth.example; +20 100 000 0007 | HR Officer |
| ISMS and evidence | ISMS Manager | isms@nabdhealth.example; +20 100 000 0008 | Engineering Manager |
| Cyber insurer | Policy contact | claims@insurer.example (simulated) | CFO |
| AWS support | AWS Support | Console case; account team | CTO |
| Regulator | Egyptian DPA | Via legal counsel | CFO |

The full contact list, including personal mobile numbers, is held in the restricted
incident folder and reviewed quarterly.

## 4. Detection sources

- Staff and contractor reports through email, Slack, or the reporting button.
- GuardDuty, CloudTrail, WAF, and CloudWatch alerts.
- Admin Panel anomaly and export alerts.
- Customer reports and support tickets.
- Supplier notifications.
- Vulnerability and penetration test findings.
- External researchers and regulators.

## 5. Severity and response targets

| Severity | Example | Acknowledge | Containment target | Escalation |
|---|---|---|---|---|
| 1 Critical | Confirmed large-scale patient data breach; ransomware; production compromise; outage over 2 hours | 15 minutes | 4 hours | CEO, board, customers, regulator, insurer |
| 2 High | Suspected patient data exposure; admin account compromise; outage 30 minutes to 2 hours | 1 hour | 8 hours | CTO, CEO, affected account manager |
| 3 Medium | Lost encrypted device; contained malware; limited exposure; degraded service | 4 business hours | 2 business days | CTO, ISMS Manager |
| 4 Low | Near miss; policy violation with no data impact | 1 business day | 5 business days | ISMS Manager |

When uncertain, assign the higher severity until triage is complete.

## 6. Response workflow

### Phase 1 — Report and acknowledge

1. The reporter contacts the channel and provides the initial report (Appendix A).
2. The on-call person acknowledges within the target and opens an incident record with a
   unique ID (`INC-YYYY-NNN`).
3. The incident commander is assigned based on severity.

### Phase 2 — Triage and assess

1. Confirm whether an incident exists and assign severity.
2. Identify affected systems, accounts, data categories, customers, and patients.
3. Determine whether personal data is involved and whether the 72-hour clock applies.
4. Preserve evidence before making changes where possible.
5. Open a decision log and notify the required people.

### Phase 3 — Contain

- Revoke sessions, tokens, and credentials.
- Disable compromised accounts and rotate secrets.
- Isolate affected systems or restrict network access.
- Block malicious indicators at WAF, DNS, or email.
- Preserve copies of logs and affected data.
- Avoid destroying evidence through rebuilds until captured.

### Phase 4 — Eradicate

- Identify and remove the root cause.
- Patch, rebuild, or reconfigure affected systems.
- Verify that persistence mechanisms are removed.
- Validate with scanning, log review, and, where needed, external support.

### Phase 5 — Recover

- Restore from a known-good backup where required (NH-PRC-004).
- Validate data integrity before returning to service.
- Monitor closely for recurrence.
- Confirm service levels and customer impact with the COO.

### Phase 6 — Notify

Use the matrix in Section 7. Notifications are factual, approved by the CEO and counsel,
and coordinated with the customer account manager. Do not speculate on cause or scope.

### Phase 7 — Learn

- Hold a post-incident review within 10 business days.
- Record timeline, root cause, impact, response effectiveness, and lessons.
- Create corrective actions in NH-NC-001 with owners and due dates.
- Update risk scores and controls.
- Report to the Security and Risk Committee and management review.

## 7. Notification matrix

| Audience | When | Owner | Channel |
|---|---|---|---|
| CEO and executives | Severity 1 or 2 immediately | Incident commander | Call and email |
| Board | Severity 1 within 24 hours | CEO | Board call and written summary |
| Affected hospital customers | Confirmed or suspected breach of their data; within 72 hours where contracted | COO | Account manager and formal notice |
| Clinics | Confirmed breach affecting their patients | COO | Email and account call |
| Data protection authority | Reportable personal data breach under PDPL | CFO with counsel | Formal regulatory channel |
| Patients | High risk to rights or data, where required | CPO with counsel | App notification and email |
| Cyber insurer | Potential claim or cover trigger | CFO | Insurer claims channel |
| Law enforcement | Criminal activity or legal requirement | CFO with counsel | As advised |
| Suppliers | Incident involves their service | CTO | Supplier security contact |

## 8. Playbooks

### 8.1 Phishing and account compromise

1. Disable the affected account and revoke sessions and tokens.
2. Reset credentials and re-enrol MFA.
3. Search for forwarding rules, mailbox rules, OAuth grants, and sent phishing.
4. Identify recipients and warn them; remove malicious messages where possible.
5. Review sign-in logs for other accounts and IP addresses.
6. If patient data was accessed, assess notification.

### 8.2 Patient data exposure

1. Identify the data, volume, patients, clinics, and cause.
2. Stop the exposure and preserve evidence.
3. Assess whether the data was accessed or only exposed.
4. Notify the CFO and counsel immediately; start the 72-hour assessment.
5. Prepare customer and patient communications with the CPO and COO.
6. Consider regulatory notification and insurer involvement.

### 8.3 Ransomware or destructive malware

1. Isolate affected systems; do not pay or communicate with the attacker without CEO and
   counsel approval.
2. Preserve evidence and identify the entry point.
3. Assess backup integrity and restore in an isolated environment.
4. Engage AWS support and, if needed, an incident response retainer.
5. Notify per the matrix; involve the insurer early.
6. Rebuild rather than clean where compromise is uncertain.

### 8.4 Platform outage with security cause

1. Confirm the cause and whether it is malicious.
2. Activate the BCP/DR plan if recovery exceeds the RTO.
3. Communicate status to customers through Support.
4. Preserve logs and change records.
5. Review change and rollback evidence after recovery.

### 8.5 Lost or stolen device

1. Revoke sessions and remote wipe the device.
2. Confirm encryption and last sign-in.
3. Assess data stored locally and whether patient data was present.
4. Report to the insurer if required and consider notification.

### 8.6 Supplier incident

1. Obtain the supplier's timeline, scope, and affected Nabd data.
2. Assess contractual notification and customer obligations.
3. Request evidence and remediation commitments.
4. Record the event in the supplier register and review the supplier rating.

## 9. Evidence and chain of custody

- Record who collected evidence, when, from where, and using what method.
- Compute hashes for files and images where practical.
- Store evidence in the restricted incident folder with read-only access.
- Use the chain-of-custody form for physical devices and media.
- Involve counsel before sharing evidence externally.
- Retain evidence per NH-POL-011 and legal hold requirements.

## 10. Communications

Templates for initial customer notice, regulatory notification, patient notice, and
internal update are held in the incident folder. All external communications require CEO
approval and legal review. The COO owns customer communication; the CPO owns patient
communication; the CFO owns regulator and insurer communication.

## 11. Testing and maintenance

- Tabletop exercise every six months; at least one involving patient data and one
  involving availability.
- Technical restoration test quarterly under NH-PRC-004.
- Contact list reviewed quarterly.
- Plan reviewed annually and after every Severity 1 or 2 incident.
- Exercise results and actions are reported in NH-KPI-001 and management review.

## 12. Appendix A — Initial incident report

| Field | Entry |
|---|---|
| Incident ID | |
| Reported by and time | |
| What happened | |
| Systems, accounts, or data affected | |
| Patients or customers potentially affected | |
| Actions already taken | |
| Evidence preserved | |
| Initial severity | |
| Incident commander | |

## 13. Appendix B — Decision log

| Time | Decision | Made by | Rationale | Follow-up |
|---|---|---|---|---|
| | | | | |

## 14. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 12 February 2027 | Initial incident response plan | CTO |
| 1.1 | 5 March 2027 | Added supplier playbook and notification matrix after exercise | CTO |
