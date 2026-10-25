# Acceptable Use and Information Handling Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-003 |
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

This policy defines acceptable use of Nabd Health systems and the classification,
labelling, handling, transfer, and disposal of information. It implements Annex A
controls A.5.10 to A.5.14, A.7.10, A.8.12, and A.8.24.

## 2. Scope

Applies to all staff and contractors using Nabd systems, devices, email, collaboration
tools, or personal devices for Nabd work, and to any third party handling Nabd
information.

## 3. Information classification

| Level | Definition | Examples | Handling |
|---|---|---|---|
| Public | Approved for public release | Website content, published policies, marketing material | No special handling; accuracy review before release |
| Internal | Routine business information not for public release | Internal procedures, meeting notes, project plans | Company systems only; share with staff and approved contractors |
| Confidential | Sensitive business or personal information | Contracts, employee records, support tickets, financial data, source code | Need-to-know; encrypted in transit and at rest; no public AI tools |
| Highly Confidential | Sensitive health data and secrets | Patient records, visit notes, lab results, scans, credentials, production keys | Strict need-to-know; logged access; no sharing outside approved systems; encryption required |

Where information could fall into two levels, the higher level applies.

## 4. Labelling

Documents, repositories, tickets, and exports must carry the classification in the
header or metadata. Patient files inherit the classification of the record they belong
to. Labels must not be removed when information is copied.

## 5. Acceptable use

### 5.1 Devices and systems

- Use Nabd-managed devices for patient data. Personal devices may access email and chat
  only through the approved MDM profile.
- Do not install unapproved software, browser extensions, or utilities on managed
  devices.
- Do not disable encryption, screen lock, endpoint protection, or MDM.
- Do not connect unauthorized removable media.
- Report lost or stolen devices immediately to IT and the incident channel.

### 5.2 Email, messaging, and collaboration

- Do not send Highly Confidential information by email unless encrypted and approved.
- Do not paste patient data into Slack, Jira, or tickets. Use the case reference and the
  minimum necessary information.
- Do not use personal email, personal cloud storage, or consumer messaging for Nabd
  information.
- Verify recipients before sending confidential information externally.

### 5.3 Internet, social media, and AI tools

- Do not use public AI assistants or translation tools with patient data, credentials,
  source code, or confidential business information.
- Do not discuss patients, customers, incidents, or internal security matters on social
  media.
- Report suspicious websites or phishing to the security channel.

### 5.4 Clear desk and clear screen

- Lock screens when leaving a device, even briefly.
- Remove patient documents and removable media from desks at the end of the day.
- Use secure print release; do not leave printed patient documents unattended.
- Whiteboards containing patient or incident information must be erased after use.

## 6. Information transfer

| Method | Permitted use | Requirement |
|---|---|---|
| Google Workspace / Drive | Internal and Confidential | Access-controlled folders; external sharing requires approval |
| Encrypted email or approved secure link | Confidential and Highly Confidential | Recipient verification; no patient data in the subject line |
| Customer portal or API | Patient and customer data | TLS 1.2 or higher; contract and DPA in place |
| Removable media | Exceptional only | CTO approval; encrypted device; register entry |
| Paper | Exceptional only | Locked storage; shredding after use |

Transfers to suppliers must be covered by a DPA and recorded in the supplier register.
Cross-border transfers require the assessment defined in NH-POL-011.

## 7. Retention and disposal

Information is retained according to the retention schedule in NH-POL-011. Paper is
cross-cut shredded; electronic media are wiped using the certified process in the
physical security policy. Deletion of patient data requires confirmation that no legal
hold applies.

## 8. Monitoring and privacy

Nabd monitors systems for security, availability, and compliance. Monitoring is
proportionate and does not extend to personal content except where necessary for an
investigation. Staff are informed of monitoring through this policy and the employee
handbook.

## 9. Reporting

Suspected phishing, lost devices, accidental disclosure, or policy violations must be
reported immediately through the incident channel. Good-faith reporting is not
disciplined.

## 10. Consequences

Violations may lead to disciplinary action, withdrawal of access, or contract
termination. Deliberate misuse of patient data may be reported to the relevant
authorities.

## 11. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-011 Data Retention and Privacy Policy
- NH-POL-013 Remote Working and Mobile Device Policy
- NH-POL-014 Cryptography and Key Management Policy
- NH-PRC-003 Incident Response Plan

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 22 January 2027 | Initial acceptable use and information handling policy | ISMS Lead Implementer |
