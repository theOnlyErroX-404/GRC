# Internal Audit Report

| Field | Value |
|---|---|
| Document ID | NH-AUD-002 |
| Version | 1.0 |
| Status | Issued |
| Audit dates | 12–16 April 2027 |
| Report date | 23 April 2027 |
| Lead auditor | Mona Ashraf, Independent Lead Auditor (contracted) |
| Distribution | CEO, CTO, COO, CFO, CPO, ISMS Manager |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This report is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Executive summary

The internal audit assessed the Nabd Health ISMS against ISO/IEC 27001:2022 clauses 4 to
10 and the applicable Annex A controls. The audit found a functioning ISMS with strong
management commitment, traceable risk treatment, and credible operational evidence.

Three **minor nonconformities** were raised:

1. Staging data masking is incomplete for three tables (A.8.11, A.8.33).
2. One leaver's Freshdesk account remained active after termination (A.5.18).
3. Two tier 1 supplier assessments were not complete (A.5.22).

No major nonconformities were found. Four observations and two opportunities for
improvement were recorded. The ISMS is assessed as **conforming and effectively
implemented**, subject to closure of the nonconformities. Certification readiness is
supported, with Nabd Health's planned Stage 1 audit (fictional).

## 2. Scope, criteria, and method

| Item | Detail |
|---|---|
| Scope | All ISMS processes and applicable Annex A controls within NH-CTX-003 |
| Period | November 2026 to April 2027 |
| Criteria | ISO/IEC 27001:2022; Nabd policies and procedures; PDPL 151/2020; customer contracts; NH-SOA-001 |
| Locations | Cairo office and remote; cloud systems reviewed remotely |
| Methods | Interviews, document review, sampling, technical verification, observation |
| Sampling | 6 leavers, 12 access records, 10 changes, 8 supplier records, 5 incidents, 4 backup and restore records, 20 controls tested |

The audit followed the plan in NH-AUD-001. The auditor is a simulated role played by
the same author; it is not a real independent audit.

## 3. Summary of findings

| ID | Type | Clause or control | Finding | Risk | Owner | Due | Status |
|---|---|---|---|---|---|---|---|
| NC-01 | Minor nonconformity | A.8.11, A.8.33 | Three of fourteen staging tables contain unmasked production data | R-12 | DevOps Lead | 2027-05-15 | Correction done; CA open |
| NC-02 | Minor nonconformity | A.5.18 | One leaver's Freshdesk account active 19 days after termination | R-02 | HR Manager / IT | 2027-04-30 | Closed 2027-04-28 |
| NC-03 | Minor nonconformity | A.5.22 | Two of seven tier 1 supplier assessments incomplete | R-15 | CFO | 2027-05-15 | In progress |
| OBS-01 | Observation | A.5.7 | Threat intelligence is informal and not linked to a collection plan | R-09, R-24 | CTO | 2027-09-30 | Open |
| OBS-02 | Observation | A.8.7 | No endpoint detection and response; EDR planned Q3 2027 | R-07, R-17 | CTO | 2027-09-30 | Open |
| OBS-03 | Observation | A.5.13 | Labelling inconsistent in legacy documents and SaaS records | R-12, R-21 | ISMS Manager | 2027-07-31 | Open |
| OBS-04 | Observation | A.8.14 | Cross-region restore not yet tested; single primary region | R-03 | CTO | 2027-06-15 | Open |
| OFI-01 | Improvement | 9.1 | Automate access review evidence collection | N/A | DevOps Lead | 2027-09-30 | Open |
| OFI-02 | Improvement | 9.1 | Add design and operating effectiveness testing to quarterly KPI | N/A | ISMS Manager | 2027-07-31 | Open |

## 4. Nonconformities

### NC-01: Incomplete staging data masking

**Requirement:** A.8.11 Data masking; A.8.33 Test information; clause 6.1.3 treatment
action T-13.

**Evidence:** The staging refresh pipeline masked 11 of 14 tables. The tables
`patient_contact`, `appointment_notes`, and `support_notes` retained production values.
The exclusion dated from a schema change in February 2027 and was not detected because
the pipeline had no coverage check. Twenty-one engineers and selected support staff had
staging access. Direct access was restricted to the VPN and logging was enabled, which
limited exposure.

**Risk:** R-12 (production data in staging). The residual score had been assessed as 6 on
the assumption that masking was complete; this is revised pending closure.

**Correction:** The three tables were masked and the staging refresh was re-run on 20
April 2027. A verification query confirmed no production values in the affected columns.

**Root cause:** The masking configuration is not tested against schema changes, and
coverage is not monitored.

**Corrective action:** Add a masking coverage test to the data pipeline that fails the
refresh if any table is unmasked; add a quarterly sample verification; record the
coverage percentage in KPI reporting. Owner: DevOps Lead. Due: 15 May 2027.

**Auditor note:** The correction is effective. The corrective action remains open until
the automated check has operated for one full refresh cycle.

### NC-02: Leaver access not removed

**Requirement:** A.5.18 Access rights; A.6.5 Responsibilities after termination; procedure
NH-PRC-001.

**Evidence:** Of six leavers sampled, one Freshdesk agent account remained active 19 days
after the last working day. The leaver's Google, AWS, and GitHub access had been removed
on time. The Freshdesk account was found during the audit and disabled on 17 April 2027.
The account had no activity after termination.

**Risk:** R-02 (former personnel retain access).

**Correction:** Account disabled and session revoked on 17 April 2027.

**Root cause:** The offboarding checklist did not list Freshdesk, and SaaS deprovisioning
relies on manual recall.

**Corrective action:** Add all SaaS tools to the checklist, reconcile the HR leaver list
against SaaS accounts monthly, and automate deprovisioning through SCIM where available.
Owner: HR Manager and IT Support Officer. Due: 30 April 2027. Verified and closed on
28 April 2027 after the updated checklist and monthly reconciliation were evidenced.

### NC-03: Tier 1 supplier assessments incomplete

**Requirement:** A.5.19, A.5.22; NH-POL-007.

**Evidence:** The supplier register showed tier 1 assessments complete for AWS, Google,
GitHub, SMSGate, and PayNile. VideoBridge and Pixelwave had no completed assessment at
the audit date. The Pixelwave contract had been revised and access restricted, and the
VideoBridge DPA was signed, so the exposure was partly mitigated.

**Risk:** R-15 (supplier breach or failure).

**Correction:** Pixelwave assessment completed 20 April 2027. VideoBridge assessment due
30 April 2027.

**Root cause:** The supplier programme was implemented in February 2027 and the review
calendar did not cover the two suppliers before the audit.

**Corrective action:** Complete both assessments, add supplier reviews to the annual
calendar with named owners, and report completion monthly in KPI-14. Owner: CFO. Due:
15 May 2027.

## 5. Observations

### OBS-01: Threat intelligence is informal

Nabd receives vendor and sector advisories and reviews GuardDuty findings, but there is
no collection plan, no defined intelligence requirements, and no record of how
intelligence changes priorities. The control is partially implemented and risk-based;
formalizing it would improve vulnerability and supplier decisions. Recommendation:
define three to five intelligence requirements and a monthly review record.

### OBS-02: No endpoint detection and response

Windows Defender and macOS protections are enabled and managed, but there is no EDR.
Given the phishing and ransomware threat to healthcare, EDR would improve detection on
endpoints. The control is partially implemented with a planned Q3 2027 rollout.

### OBS-03: Labelling inconsistent

Classification labels are applied to templates, repositories, and new documents, but
legacy documents and some SaaS records are unlabelled. Recommendation: label on touch
and add a metadata field to the document template.

### OBS-04: Cross-region restore not tested

The Q1 restore test proved recovery in the primary region. Cross-region recovery remains
untested, which limits assurance against a regional outage. The test is scheduled for
15 June 2027 and is tracked under R-03.

## 6. Opportunities for improvement

- **OFI-01:** Automate the collection of access review evidence (user lists, HR
  comparison, decisions) to reduce manual effort and improve consistency.
- **OFI-02:** Introduce quarterly design and operating effectiveness testing for a
  rotating sample of controls, so that issues are found before the annual audit.

## 7. Positive practices

- Visible CEO sponsorship and a functioning Security and Risk Committee.
- Risk register entries trace to gaps, assets, controls, and treatment actions.
- The backup restore test included integrity checks, tenant isolation, and evidence
  destruction.
- Awareness completion is 100 percent, and phishing click rates improved from 8.1 to 3.4
  percent.
- The supplier register and contract amendments materially improved supplier control.
- Staff interviewed understood how to report incidents and why patient data handling
  matters.

## 8. Conclusion

The ISMS conforms to ISO/IEC 27001:2022 with three minor nonconformities and is
effectively implemented. No major nonconformity was identified. The nonconformities are
capable of closure within the agreed dates and do not prevent the Stage 1 certification
audit from proceeding.

**Recommendation:** proceed with Nabd Health's planned Stage 1 audit (fictional),
subject to closure of NC-01 and NC-03 and completion of the open treatment actions for
R-12, R-15, and R-22.

## 9. Appendix: Controls sampled

A.5.1, A.5.2, A.5.9, A.5.10, A.5.12, A.5.15, A.5.17, A.5.18, A.5.19, A.5.20, A.5.22,
A.5.24, A.5.26, A.5.29, A.5.30, A.5.33, A.5.34, A.5.35, A.6.3, A.6.5, A.6.7, A.7.2,
A.7.4, A.7.7, A.7.14, A.8.1, A.8.2, A.8.5, A.8.8, A.8.11, A.8.13, A.8.15, A.8.16,
A.8.24, A.8.25, A.8.29, A.8.32, A.8.33.

## 10. Sign-off

**Mona Ashraf**
Independent Lead Auditor (simulated)

23 April 2027

## 11. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 23 April 2027 | Initial audit report issued | Lead Auditor |
