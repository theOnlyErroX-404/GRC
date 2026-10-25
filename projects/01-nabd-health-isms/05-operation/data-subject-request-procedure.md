# Data Subject Request Procedure

| Field | Value |
|---|---|
| Document ID | NH-PRC-008 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 31 March 2027 |
| Owner | Heba Youssef, CFO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This procedure is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. It is not
> legal advice; PDPL timelines and exemptions must be confirmed by counsel.

## 1. Purpose

This procedure defines how Nabd Health receives, verifies, and responds to data subject
requests under the Egyptian Personal Data Protection Law No. 151 of 2020, and how it
coordinates requests relating to data controlled by clinics. It supports A.5.34 and
NH-POL-011.

## 2. Scope

Applies to requests from patients, employees, contractors, clinic staff, and other
individuals whose personal data Nabd processes, including access, correction, deletion,
restriction, objection, and portability requests.

## 3. Channels and roles

| Role | Responsibility |
|---|---|
| DPO | Point of contact, decides on complex requests, liaises with the regulator |
| CFO | Owns the procedure and legal coordination |
| Support | Receives patient requests and records them |
| HR | Handles employee requests |
| Engineering | Provides data extracts or deletion evidence |
| Clinic relationship owner | Coordinates controller-controlled requests with the clinic |
| Legal counsel | Advises on exemptions, identity, and refusal |

Requests may arrive by email to `privacy@nabdhealth.example` (simulated), through the
patient app, through a clinic, or by post. Staff must forward any request to the DPO
within one business day.

## 4. Process

1. **Log**: create a request record with ID `DSR-YYYY-NNN`, date, channel, requester,
   and request type.
2. **Acknowledge**: confirm receipt within the period required by PDPL and explain the
   next steps.
3. **Verify identity**: use proportionate verification. Do not collect more data than
   necessary. For patient data, verify against the registered phone number or clinic
   confirmation.
4. **Determine the role**: if Nabd is a processor, forward the request to the clinic as
   controller and support the response. If Nabd is the controller, handle it directly.
5. **Assess**: identify the data, legal basis, exemptions, and any third-party rights.
6. **Fulfil**: provide a copy, correct, delete, restrict, or explain why the request
   cannot be met. Use secure delivery.
7. **Record**: document the decision, actions, and evidence.
8. **Close**: inform the requester of the outcome and their right to complain to the
   regulator.

## 5. Timelines

| Step | Target |
|---|---|
| Log and acknowledge | 2 business days |
| Identity verification | 5 business days |
| Controller referral | 3 business days |
| Complete straightforward request | 30 days, or the period required by PDPL |
| Complex request | Extension with written explanation where permitted |
| Refusal | Written reasons and complaint route |

The DPO monitors the queue weekly and escalates overdue requests to the CFO.

## 6. Access requests

- Confirm the scope of data and the systems involved (RDS, S3, Freshdesk, HubSpot,
  Google Workspace).
- Export only the requester's data; redact third-party data.
- Provide a clear format and explain codes or attachments.
- Do not disclose data that would harm another person or breach a legal obligation.
- Record the export and delivery.

## 7. Correction and deletion

- Correction requires evidence where accuracy is disputed.
- Deletion is performed where there is no legal or contractual retention obligation.
- If deletion is not possible, explain the retention basis and restrict processing where
  appropriate.
- Deletion from backups follows the backup expiry schedule and is documented.
- Clinic-controlled records are corrected or deleted by the clinic; Nabd supports the
  technical action.

## 8. Objection and restriction

Where processing is objected to, the DPO assesses the legal basis and pauses processing
if required. Restrictions are implemented in the application or by access control until
the request is resolved.

## 9. Security

- Verify identity before disclosing any data.
- Deliver data through an approved secure channel, not ordinary email where sensitive.
- Do not discuss requests with anyone who is not involved.
- Record all access to the request file.

## 10. Refusals and complaints

If a request is refused, the DPO provides written reasons, the legal basis, and the route
to complain to the data protection authority. Refusals are reviewed by counsel. The
requester is not charged unless the law permits and the request is manifestly unfounded
or excessive.

## 11. Records and reporting

The DSR register records the request ID, type, dates, outcome, and evidence. A quarterly
summary is reported to management review, including volume, timeliness, and issues. The
register is retained for three years.

## 12. Related documents

- NH-POL-011 Data Retention and Privacy Policy
- NH-POL-003 Acceptable Use and Information Handling Policy
- NH-POL-006 Incident Management Policy
- NH-PRC-003 Incident Response Plan

## 13. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 31 March 2027 | Initial data subject request procedure | CFO |
