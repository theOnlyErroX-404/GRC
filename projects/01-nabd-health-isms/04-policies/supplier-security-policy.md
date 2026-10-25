# Supplier Security Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-007 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 12 February 2027 |
| Owner | Heba Youssef, CFO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy governs information security in supplier relationships, from selection and
contracting through monitoring and exit. It implements Annex A controls A.5.19 to
A.5.23 and A.8.30.

## 2. Scope

Applies to all suppliers, vendors, contractors, and service providers that access Nabd
information, process it on Nabd's behalf, or support in-scope services. The supplier
register (NH-REG-003) lists all current suppliers.

## 3. Supplier tiering

| Tier | Definition | Examples | Due diligence |
|---|---|---|---|
| 1 Critical | Processes patient data or can cause material service loss | AWS, Google, GitHub, SMSGate, VideoBridge, PayNile, Pixelwave | Full security assessment, DPA, assurance reports, annual review, right to audit |
| 2 Important | Accesses confidential data or supports operations | Freshdesk, Slack, Atlassian, payroll provider, law firm | Security questionnaire, DPA where personal data, biennial review |
| 3 Low | Limited data access or low impact | Figma, landlord, ISP | Basic checks, contract terms, review on change |

Tiering is reviewed when the service, data access, or criticality changes.

## 4. Selection and due diligence

Before contracting a tier 1 or tier 2 supplier:

1. The business owner completes a supplier risk assessment using the standard
   questionnaire.
2. Security, privacy, financial, and continuity risk are assessed.
3. Evidence is collected: certifications, assurance reports, penetration test summaries,
   DPA, subprocessor list, and breach history.
4. The CFO and CTO review the assessment; tier 1 also requires CEO awareness.
5. Unresolved high risks must be mitigated by contract or compensating control before
   approval.

Cloud providers may be assessed using recognized assurance reports instead of a full
questionnaire, provided the report scope covers the service used.

## 5. Contract requirements

Contracts with tier 1 and tier 2 suppliers must include, proportionate to risk:

- confidentiality and non-disclosure;
- security requirements and applicable standards;
- data protection terms and permitted subprocessors;
- breach notification timelines;
- right to audit or receive audit evidence;
- access control and personnel screening commitments;
- data return and deletion on termination;
- liability and indemnity for security breaches;
- service levels and continuity requirements;
- cooperation with regulators and incident response.

Legacy contracts that lack these terms must be amended at renewal or earlier where the
risk is high. The Pixelwave agreement was amended in February 2027.

## 6. Monitoring and review

| Activity | Frequency | Owner |
|---|---|---|
| Tier 1 security review and assurance evidence | Annual | CFO |
| Tier 2 questionnaire review | Every two years | CFO |
| Service level review | Quarterly for critical services | Service owner |
| Incident and breach review | After each event | CTO |
| Subprocessor change review | On notification | CFO |
| Contract renewal review | Before renewal | CFO |

Review results are recorded in the supplier register with a risk rating and actions.
Poor performance or unresolved risk triggers a remediation plan or exit assessment.

## 7. Cloud services

For cloud services, Nabd defines its responsibilities under the shared responsibility
model, configures the service securely, monitors changes, and retains exit plans for
critical data. The AWS, Google, and GitHub configurations are reviewed at least annually.

## 8. Outsourced development

Pixelwave developers:

- are bound by a confidentiality and security schedule;
- receive only the access required for the mobile repositories and staging;
- are subject to Nabd code review and release approval;
- must use devices that meet the minimum requirements in NH-POL-013;
- are removed from access at the end of the engagement.

Nabd remains accountable for the security of the code and data.

## 9. Supplier incidents

Suppliers must notify Nabd without undue delay when an incident affects Nabd data or
services. Nabd assesses the impact, notifies customers where required, and records the
event in the incident register. Repeated failures affect the supplier risk rating.

## 10. Exit

Before terminating a critical supplier, the owner must confirm:

- return or deletion of Nabd data;
- revocation of access and credentials;
- transfer of records and evidence;
- continuity of service during transition;
- retention obligations.

Exit is recorded in the supplier register.

## 11. Related documents

- NH-POL-001 Information Security Policy
- NH-POL-006 Incident Management Policy
- NH-POL-011 Data Retention and Privacy Policy
- NH-REG-003 Supplier Register
- 05-operation/supplier-register.csv

## 12. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 12 February 2027 | Initial supplier security policy | ISMS Lead Implementer |
