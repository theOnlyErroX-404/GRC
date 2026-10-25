# Context of the Organization and Issues

| Field | Value |
|---|---|
| Document ID | NH-CTX-001 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 20 November 2026 |
| Owner | ISMS Lead Implementer |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This document is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This document records the external and internal issues that affect Nabd Health's ability
to achieve the intended outcomes of its information security management system (ISMS),
as required by ISO/IEC 27001:2022 clause 4.1. It also records the method used, the
resulting SWOT position, and how each issue is carried into the risk assessment and the
ISMS scope.

## 2. Method

The issues were identified between 2 and 13 November 2026 through:

- Interviews with the CEO, COO, CTO, CFO, CPO, Engineering Manager, DevOps Lead,
  Head of Support, HR Manager, IT Support Officer, and Head of Sales.
- Review of the baseline fact base (NH-FB-001), customer contracts, tender documents,
  the insurance application, and the prior incidents of March and August 2026.
- A PESTLE scan of the external environment and a SWOT synthesis.
- Review of the legal and contractual context in Section 14 of the fact base; legal
  status of each item remains subject to confirmation by external counsel.

Issues are reviewed at least annually and whenever a significant change occurs. Each
issue is assigned to an owner and, where it creates uncertainty, linked to one or more
risks in the risk register (NH-REG-002).

## 3. External issues

| ID | Category | Issue | Effect on the ISMS | Linked risks | Owner |
|---|---|---|---|---|---|
| E-01 | Market | Three active hospital tenders require ISO/IEC 27001 certification or a credible certification timeline | Certification is a commercial requirement, not only good practice. Scope and timeline must support June 2027 stage 1 audit | R-13 | CEO |
| E-02 | Legal | Egyptian Personal Data Protection Law No. 151 of 2020 and its executive regulations apply to personal and sensitive health data | Requires lawful basis, security measures, breach handling, records of processing, and assessment of cross-border transfer to Bahrain | R-16, R-22 | CFO / CTO |
| E-03 | Legal | Anti-Cyber and Information Technology Crimes Law No. 175 of 2018 imposes service-provider duties and data retention obligations | Log retention and cooperation with authorities must be defined | R-08, R-22 | CFO |
| E-04 | Regulatory | Ministry of Health and Population rules on health data and telemedicine are not yet confirmed by counsel | Telemedicine data flows and records retention may need adjustment | R-22 | CFO |
| E-05 | Regulatory | Central Bank of Egypt requirements may apply to payment flows handled through PayNile | Payment data must remain out of scope of Nabd systems and be contractually controlled | R-15, R-22 | CFO |
| E-06 | Contractual | Nine customer contracts promise 99.9 percent availability; five hospital contracts require breach notification within 72 hours; three grant audit rights | Service continuity, incident response, and evidence access become contractual obligations | R-03, R-11, R-23 | COO |
| E-07 | Investor | Series B due diligence will examine security governance and risk management | The ISMS must be credible and evidenced, not a document set | R-13 | CEO |
| E-08 | Insurance | The 2025 cyber insurance application declared MFA enforced for all staff, which is inaccurate | The declaration must be corrected; misrepresentation could void cover | R-01 | CFO |
| E-09 | Threat | Healthcare platforms are targeted by phishing, credential stuffing, ransomware, and data theft for extortion | Controls must prioritize identity, endpoint, monitoring, and recovery | R-01, R-06, R-08, R-09 | CTO |
| E-10 | Technical | All production workloads run in one AWS region (me-south-1) under a single organization | Regional outage or account compromise has an outsized effect; recovery must be planned explicitly | R-03, R-23, R-24 | CTO |
| E-11 | Supply chain | Critical services depend on AWS, GitHub, Google, Pixelwave, SMSGate, VideoBridge, and PayNile | Supplier security and contractual controls are required, including for the Bahrain hosting arrangement | R-05, R-15, R-24 | CFO / CTO |
| E-12 | Labour market | Nine leavers in the last 12 months and competition for engineers | Access removal and knowledge continuity are recurring operational risks | R-02, R-25 | HR Manager |
| E-13 | Economic | EGP 1.2 million budget approved for tools and certification; cost pressure on tooling | Controls must be proportionate and prioritized by risk | R-13 | CFO |

## 4. Internal issues

| ID | Category | Issue | Effect on the ISMS | Linked risks | Owner |
|---|---|---|---|---|---|
| I-01 | Governance | No CISO, no DPO, no security committee; security handled informally by the DevOps Lead | Accountability and decision-making must be assigned before certification | R-13 | CEO |
| I-02 | People | 60 employees and 3 outsourced developers; hybrid working, about 40 percent remote on a typical day | Remote access, endpoint control, and awareness are in scope | R-06, R-07, R-17 | COO |
| I-03 | Technology | Cloud-native platform on AWS with Terraform, ECS, RDS, S3, and GitHub Actions | Controls must fit infrastructure-as-code and CI/CD rather than assume on-premises tooling | R-09, R-18, R-24 | CTO |
| I-04 | Data | About 412,000 patient records, 2.8 million clinical entries, and 6.5 TB of patient files | Confidentiality and integrity failures have direct patient and regulatory impact | R-04, R-12, R-16, R-22 | CPO |
| I-05 | Security baseline | 22 known gaps recorded in the fact base, including MFA, offboarding, backups, monitoring, and unmasked staging data | The gap baseline drives the risk register and treatment plan | All | CTO |
| I-06 | Documentation | No information security policy, risk assessment, incident plan, or BC/DR plan; architecture page outdated | The ISMS documentation set must be built and approved | R-13 | ISMS Lead |
| I-07 | Identity | MFA optional for staff and admins; GitHub organization 2FA not required; two former contractors retain access | Account compromise and unauthorized code access are credible | R-01, R-02, R-10 | CTO |
| I-08 | Support access | Support staff can view any patient record through the Admin Panel; record views are not logged | Insider and support-account misuse is difficult to detect | R-04 | Head of Support |
| I-09 | Environments | Production data is copied to staging monthly without masking | A staging compromise would expose live patient data | R-12 | DevOps Lead |
| I-10 | Detection | CloudWatch retention is 30 days, GuardDuty alerts go to an unmonitored channel, no SIEM | Intrusions may not be detected or investigated in time | R-08 | DevOps Lead |
| I-11 | Continuity | Backups exist but restores are untested; no RPO, RTO, BCP, or DR plan | Contracted availability and recovery expectations cannot be demonstrated | R-03, R-23 | CTO |
| I-12 | Culture | Security is viewed as an IT task; the March 2026 phishing incident produced no lasting change | Awareness and reporting behaviour must be actively managed | R-06 | COO |
| I-13 | Key-person dependency | The DevOps Lead is the single point of knowledge for AWS, CI/CD, and the bastion host | Unavailability of one person can block recovery and change | R-25 | CTO |
| I-14 | Growth | Customer base and headcount are growing; new clinics onboard monthly | Access, asset, and supplier processes must scale rather than rely on memory | R-15, R-18 | CEO |

## 5. SWOT synthesis

| Strengths | Weaknesses |
|---|---|
| Cloud-native architecture with infrastructure as code; Multi-AZ production; TLS and encryption at rest in place; GuardDuty in production; organization CloudTrail with one-year retention | 22 baseline gaps concentrated in identity, offboarding, monitoring, recovery, and supplier governance; no ISMS roles or documentation; over-broad support access |
| **Opportunities** | **Threats** |
| ISO 27001 certification supports three hospital tenders and Series B diligence; AWS and SaaS compliance reports can be reused as supplier evidence; automation can make access and backup controls repeatable | Phishing and credential theft; ransomware against healthcare; regulatory action under PDPL; contract penalties for availability; loss of customer trust after a breach |

## 6. Implications for the ISMS

1. **Scope must follow the contracts and data flows**, not the org chart. The platform,
   its AWS accounts, the Cairo office, and remote working are in scope; marketing
   activities and Pixelwave's premises are excluded with justification (NH-CTX-003).
2. **Identity and access is the first treatment priority.** MFA, offboarding, privileged
   access, and Admin Panel logging address the highest-scoring risks and the insurance
   declaration.
3. **Recovery must be evidenced.** Untested backups and the absence of RPO/RTO are
   incompatible with 99.9 percent contractual commitments.
4. **Supplier controls must cover the Bahrain hosting decision and the Pixelwave
   contract**, including data protection terms and audit rights.
5. **The ISMS must survive scrutiny.** Documents will be backed by operational records
   and internal audit evidence, not statements of intent.

## 7. Review and revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 20 November 2026 | Initial issue register approved as part of ISMS context | ISMS Lead Implementer |

Next scheduled review: November 2027, or earlier after a significant change, incident,
or regulatory update.
