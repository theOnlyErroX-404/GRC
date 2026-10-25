# Data Retention and Privacy Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-011 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 26 February 2027 |
| Owner | Heba Youssef, CFO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. It is not
> legal advice; the PDPL position must be confirmed by Egyptian counsel.

## 1. Purpose

This policy defines how Nabd Health retains, deletes, and protects personal and business
information, and how it meets its obligations under Egyptian Personal Data Protection Law
No. 151 of 2020 (PDPL) and its customer contracts. It implements Annex A controls
A.5.31, A.5.33, A.5.34, A.8.10, and A.8.12.

## 2. Scope

Applies to all personal data and business records in scope of the ISMS, including patient
data, employee data, customer data, support records, logs, backups, and supplier records.

## 3. Roles

Nabd acts as:

- a **processor** for patient data that clinics and hospitals control;
- a **controller** for its own staff data, patient app accounts, support records, and
  marketing data (marketing is outside the ISMS scope but remains subject to PDPL).

The CFO is the privacy lead. A Data Protection Officer was appointed in March 2027 and
acts as the point of contact for data subjects and the regulator.

## 4. Privacy principles

1. **Lawfulness and fairness**: process data only for a documented purpose and lawful
   basis.
2. **Purpose limitation**: do not use patient data for secondary purposes without a
   lawful basis.
3. **Minimization**: collect and retain only what is necessary.
4. **Accuracy**: provide mechanisms to correct inaccurate data.
5. **Storage limitation**: delete or anonymize data when the retention period ends.
6. **Integrity and confidentiality**: apply the controls in this ISMS.
7. **Accountability**: maintain records of processing, DPIA, and evidence.

## 5. Records of processing

The CFO maintains records of processing activities covering:

- the purpose and lawful basis;
- data categories and data subjects;
- recipients, processors, and subprocessors;
- cross-border transfers and safeguards;
- retention periods;
- security measures.

Records are reviewed annually and when a new processing activity, supplier, or
jurisdiction is introduced.

## 6. Retention schedule

| Data category | Retention | Basis | Disposal |
|---|---|---|---|
| Patient clinical records | Per clinic contract and applicable health record rules; default 10 years after last visit | Contract and health regulation | Secure deletion with certificate |
| Patient account and app data | 2 years after account closure | Contract and PDPL | Secure deletion |
| Uploaded patient files | Same as clinical record | Contract | Secure deletion |
| Telemedicine session metadata | 2 years | Contract and operational need | Secure deletion |
| Payment transaction records | 7 years | Tax and financial law | Secure deletion |
| Clinic contracts and billing | 7 years after contract end | Contract and tax law | Secure deletion |
| Employee records | Employment period plus 7 years | Labour and tax law | Secure deletion |
| Support tickets | 3 years, with patient details minimized | Operational need | Secure deletion |
| Security and audit logs | 12 months, or 3 years for incidents | Security and legal need | Secure deletion |
| Backups | Per NH-POL-008 | Recovery need | Expiry and secure deletion |
| Candidate records | 12 months after decision | Consent or legitimate interest | Secure deletion |
| Marketing leads | Per privacy notice | Consent | Secure deletion |

Legal holds suspend deletion for the affected records. The hold must be documented,
approved by the CFO, and reviewed every six months.

## 7. Deletion

1. Automated jobs delete data at the end of the retention period.
2. Deletion is logged with the data category, volume, date, and job reference.
3. Backups expire on schedule; deletion from backups is not immediate but is documented.
4. Deletion from third-party systems is confirmed with the supplier where required.
5. Where data cannot be deleted, it is anonymized and the reason is recorded.

## 8. Data subject rights

Nabd provides a procedure (NH-PRC-008) for requests to access, correct, delete, restrict,
or object to processing, and for data portability where applicable. Requests are
acknowledged within the period required by PDPL and completed without undue delay.
Identity is verified before action. Requests relating to clinic-controlled data are
coordinated with the clinic as controller.

## 9. Cross-border transfers

Patient data is hosted in AWS Bahrain (me-south-1). Before any transfer, Nabd assesses:

- the legal basis and PDPL transfer requirements;
- the destination's protections and supplier safeguards;
- contractual terms and subprocessors;
- the ability to meet data subject rights and breach obligations.

The assessment is approved by the CFO with legal advice and reviewed annually or when
the hosting location changes. Transfers that cannot be safeguarded are not permitted.

## 10. Data protection impact assessment

A DPIA is required before:

- a new processing activity involving sensitive data;
- a new technology or supplier that changes data flows;
- a cross-border transfer;
- a change that affects patient rights or the sensitivity of data.

The DPIA records necessity, risks to data subjects, safeguards, and the decision. The
DPIA for the platform and the Bahrain transfer was completed in April 2027.

## 11. Breach notification

Personal data breaches are handled under NH-POL-006. The CFO, with counsel, determines
whether notification to the regulator or data subjects is required and ensures
contractual notifications are issued within the required time.

## 12. Supplier and processor management

Processors must be bound by a DPA, provide sufficient guarantees, and notify Nabd of
subprocessors and breaches. Supplier compliance is reviewed under NH-POL-007.

## 13. Related documents

- NH-POL-003 Acceptable Use and Information Handling Policy
- NH-POL-006 Incident Management Policy
- NH-POL-007 Supplier Security Policy
- NH-POL-008 Backup, Continuity and Recovery Policy
- NH-PRC-008 Data Subject Request Procedure
- NH-REG-003 Supplier Register

## 14. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 26 February 2027 | Initial retention and privacy policy | CFO |
