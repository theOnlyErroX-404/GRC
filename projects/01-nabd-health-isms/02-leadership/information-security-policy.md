# Information Security Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-001 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 15 December 2026 |
| Owner | Karim Salah, CEO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | December 2027 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy establishes Nabd Health's commitment to protecting the confidentiality,
integrity, and availability of the information it handles, and defines the principles
and governance for the Information Security Management System (ISMS).

Nabd Health processes sensitive health data for 118 clinics, 6 hospital groups, and
about 412,000 patients. A security failure can harm patients, breach patient and
customer trust, violate Egyptian law, and prevent the company from winning hospital
contracts. Information security is therefore a business requirement, not an IT
function.

## 2. Scope

This policy applies to:

- All employees, executives, and contractors of Nabd Health, including outsourced
  developers working under supervision.
- All information and assets within the ISMS scope defined in NH-CTX-003.
- All systems, suppliers, and locations used to develop, host, operate, or support the
  Nabd Platform.
- Any third party granted access to Nabd information or systems.

## 3. Policy statement

Nabd Health will:

1. **Protect patient and customer data.** Apply controls proportionate to the
   sensitivity of health, personal, payment, and employee data, and meet its obligations
   under Egyptian Personal Data Protection Law No. 151 of 2020 and its contracts.
2. **Set clear accountability.** Assign an owner for the ISMS, for each risk, and for
   each information asset. Security responsibilities are part of normal job roles.
3. **Manage risk explicitly.** Identify, assess, treat, and monitor information security
   risks using the methodology in NH-RISK-001, and maintain a Statement of Applicability
   that justifies every Annex A decision.
4. **Enforce strong identity and access control.** Require multi-factor authentication
   for administrative and remote access, grant least privilege, review access regularly,
   and remove access promptly when people leave.
5. **Engineer security into change.** Apply secure development, code review, dependency
   management, testing, and controlled change management to production systems.
6. **Detect and respond.** Maintain logging and monitoring, an incident response
   capability, and reporting channels that allow staff and contractors to raise concerns
   without fear of blame for good-faith reporting.
7. **Be ready to recover.** Maintain tested backups, defined recovery objectives, and a
   business continuity and disaster recovery capability aligned with contractual
   availability commitments.
8. **Manage suppliers.** Assess security before contracting, include security and data
   protection terms, monitor performance, and retain the right to audit critical
   suppliers.
9. **Build awareness.** Train all staff and contractors at onboarding and at least
   annually, and test resilience against phishing and social engineering.
10. **Comply and improve.** Meet legal, regulatory, contractual, and certification
    requirements; measure performance; conduct internal audits and management reviews;
    and correct nonconformities.
11. **Protect evidence and records.** Retain security records for defined periods and
    handle electronic evidence lawfully.
12. **Provide resources.** Fund the ISMS, assign competent people, and give top
    management attention to security risk.

## 4. Policy principles

- **Risk-based:** controls are prioritized by risk to patients, customers, and the
  business, not by checklist completeness.
- **Traceable:** every risk, control, and audit finding is linked to the fact base, an
  asset ID, a gap ID, or a legal or contractual requirement.
- **Proportionate:** controls fit a 60-person cloud-native company and do not create
  unusable bureaucracy.
- **Evidence-led:** a control is only considered effective when there is objective
  evidence that it operates.
- **Accountable:** every activity has a named owner and a defined review cycle.

## 5. Policy hierarchy

| Level | Purpose | Examples |
|---|---|---|
| Policy | States intent and mandatory requirements | This policy |
| Standard | Defines specific, measurable requirements | Access control, logging, configuration baselines |
| Procedure | Describes how to perform an activity | Onboarding, offboarding, incident response, restore testing |
| Guideline | Recommended practice, not mandatory | Secure coding guidance, awareness material |

Topic-specific policies are listed in the document index in the repository README. Where
a topic-specific policy conflicts with this policy, this policy prevails unless the CEO
approves a documented exception.

## 6. Roles and responsibilities

| Role | Responsibility |
|---|---|
| CEO | ISMS sponsor; approves policy, risk appetite, and material risk acceptance; chairs management review |
| CTO | Owns technology risk and the ISMS operationally; approves technical standards and exceptions within delegated authority |
| ISMS Manager | Maintains the ISMS, coordinates risk assessment, internal audit, and corrective actions; reports performance |
| Risk owners | Assess and treat the risks assigned to them; provide evidence of treatment |
| Asset owners | Maintain asset information and approve access to their assets |
| Engineering Manager | Ensures secure development and change practices are followed |
| DevOps Lead | Operates production controls: access, backups, monitoring, vulnerability management |
| Head of Support and Operations | Controls Admin Panel use and patient-data handling in support |
| HR Manager | Runs screening, onboarding, awareness, and offboarding |
| CFO | Owns supplier contracts, legal and regulatory coordination, insurance, and privacy governance |
| All staff and contractors | Follow policy, protect assets, report incidents and weaknesses promptly |

Detailed accountabilities and a RACI for ISMS activities are in NH-ROL-001.

## 7. Compliance and exceptions

Compliance is monitored through access reviews, control operation records, KPIs
(NH-KPI-001), internal audit, and management review. Deliberate or repeated violations
may lead to disciplinary action under the employee handbook and, for contractors,
contract termination.

Exceptions to this policy or a topic-specific policy must be:

- requested in writing with the business justification and compensating controls;
- approved by the CTO for low and medium risk, and by the CEO for high or critical risk;
- recorded in the risk register or exception log with an expiry date;
- reviewed at management review.

No exception may be used to avoid a legal or contractual obligation without advice from
counsel.

## 8. Communication and awareness

This policy is communicated to all staff and contractors at onboarding and annually,
published on the company intranet, and referenced in awareness training. Customers and
other interested parties may receive a summary on request, subject to confidentiality.

## 9. Review

This policy is reviewed at least annually, and after a material incident, regulatory
change, organizational change, or audit finding. The CEO approves revisions.

## 10. Approval

Approved for issue on 15 December 2026.

**Karim Salah**
Chief Executive Officer, Nabd Health (simulated)

## 11. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 15 December 2026 | Initial information security policy approved | ISMS Lead Implementer |
