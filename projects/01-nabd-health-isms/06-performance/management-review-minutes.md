# Management Review Minutes

| Field | Value |
|---|---|
| Document ID | NH-MR-001 |
| Version | 1.0 |
| Status | Approved |
| Meeting date | 29 April 2027, 10:00–12:30 (simulated) |
| Location | Cairo office and video conference |
| Chair | Karim Salah, CEO |
| Minutes by | ISMS Manager |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. These minutes are part of a simulated
> ISO/IEC 27001:2022 implementation and do not describe a real organization.

## 1. Attendees

| Name | Role | Present |
|---|---|---|
| Karim Salah | CEO (chair) | Yes |
| Omar Nasser | CTO | Yes |
| Dina Mostafa | COO | Yes |
| Heba Youssef | CFO | Yes |
| Layla Hamdy | CPO | Yes |
| Sara Lotfy | Engineering Manager | Yes |
| Nour El-Din Abbas | Head of Support and Operations | Yes |
| Mariam Khalil | HR Manager | Yes |
| Rania Fouad | Office Manager | Remote |
| ISMS Manager | ISMS lead | Yes |
| Mona Ashraf | Independent auditor (item 5 only) | Remote |

Apologies: none.

## 2. Purpose

The review fulfils ISO/IEC 27001:2022 clause 9.3. It considers the continuing
suitability, adequacy, and effectiveness of the ISMS, and decides on improvement and
resources.

## 3. Inputs reviewed

### 3.1 Status of actions from the previous review

This is the first formal management review. No previous actions exist; the project
actions from the implementation plan were reviewed instead. All 47 treatment actions were
reviewed, with 43 complete and 4 open (T-04, T-13, T-17, T-44).

### 3.2 Changes in external and internal issues

- The three hospital tenders remain active and require certification or a credible
  timeline.
- PDPL guidance and the cross-border transfer position are still under legal review.
- The Series B process is expected to start in Q4 2027; security diligence will be
  required.
- Headcount is stable at 60; one support role is being recruited.
- No change to the ISMS scope is proposed.

### 3.3 Interested-party feedback

- Two hospital customers requested the certification timeline and the latest
  penetration test summary. Both were provided under NDA.
- No patient complaints related to privacy were received in Q1 2027.
- The cyber insurer acknowledged the corrected MFA declaration.
- Staff feedback highlighted that the incident reporting button is easy to use.

### 3.4 Performance and effectiveness

| Area | Result | Assessment |
|---|---|---|
| Critical and High risks above appetite | 0 of 26 | Effective |
| Treatment actions on time | 91 percent (43/47) | Effective; 4 open |
| MFA coverage | 100 percent | Effective |
| Leaver access removed on time | 83 percent in Q1; 100 percent in April | Needs improvement; NC-02 closed |
| Critical vulnerability SLA | 100 percent | Effective |
| Backup restore test | Passed 14 March 2027 | Effective in primary region; cross-region untested |
| Phishing click rate | 3.4 percent | Improving |
| Awareness completion | 100 percent | Effective |
| Tier 1 supplier assessments | 5 of 7 at audit; 6 of 7 at review | Improving; NC-03 open |
| Platform availability | 99.93 percent Q1 | Within contract |
| Data subject requests | 3 of 3 on time | Effective |
| Audit nonconformities | 3 minor; 1 closed | Acceptable; 2 open |

### 3.5 Internal audit results

The auditor presented the report (NH-AUD-002). She confirmed no major nonconformity, three
minor nonconformities, four observations, and two opportunities for improvement. She
recommended proceeding to Stage 1 subject to closure of NC-01 and NC-03.

### 3.6 Risk assessment and treatment

The risk register remains at 26 risks. No new Critical or High risk emerged in Q1. R-12
(staging masking) and R-15 (supplier assessments) remain in treatment and are linked to
the audit findings. R-22 (PDPL) remains in treatment pending the DPIA and transfer
assessment. Residual scores for these risks are provisional.

### 3.7 Incidents

| Incident | Severity | Summary | Status |
|---|---|---|---|
| INC-2027-001 | Low | Phishing email reported by two staff; no credentials entered | Closed |
| INC-2027-002 | Low | Lost personal phone with email profile; remote wipe completed | Closed |
| INC-2027-003 | Low | Misconfigured staging security group briefly allowed wider access; corrected within 40 minutes | Closed |

No reportable personal data breach occurred. Lessons were recorded, and the staging
security group is now managed in Terraform with a drift alert.

### 3.8 Adequacy of resources

The ISMS Manager allocation of 20 percent after certification is adequate for routine
operation but tight during audit preparation. The CTO requested a temporary increase to
40 percent for May and June 2027. The CEO approved.

### 3.9 Supplier performance

AWS, Google, and GitHub performance was satisfactory. SMSGate delivery issues in January
were resolved. The VideoBridge assessment is the only outstanding tier 1 item.

## 4. Decisions and actions

| ID | Decision or action | Owner | Due | Status |
|---|---|---|---|---|
| MR-01 | Close NC-02 as verified; retain NC-01 and NC-03 as open | ISMS Manager | 2027-04-30 | Complete |
| MR-02 | Approve application for Stage 1 certification audit in June 2027 | CEO | 2027-05-07 | Open |
| MR-03 | Complete the masking coverage test and quarterly verification (NC-01) | DevOps Lead | 2027-05-15 | Open |
| MR-04 | Complete the VideoBridge supplier assessment (NC-03) | CFO | 2027-05-15 | Open |
| MR-05 | Complete the DPIA and Bahrain transfer assessment | CFO | 2027-05-15 | Open |
| MR-06 | Commission the cross-region restore test | CTO | 2027-06-15 | Open |
| MR-07 | Approve EDR budget of EGP 180,000 and Q3 rollout | CEO | 2027-06-30 | Open |
| MR-08 | Increase ISMS Manager allocation to 40 percent for May and June | CEO | 2027-05-01 | Complete |
| MR-09 | Add masking coverage and supplier review completion to the monthly KPI pack | ISMS Manager | 2027-05-01 | Open |
| MR-10 | Review the risk register and residual acceptance after NC closure | CTO | 2027-05-31 | Open |
| MR-11 | Schedule the next management review for July 2027 | ISMS Manager | 2027-07-15 | Open |

## 5. Risk appetite and scope

The risk appetite and acceptance criteria in NH-RISK-001 remain appropriate for the
current business context. The ISMS scope in NH-CTX-003 remains valid. The review
confirmed that no excluded activity has become material to the scope.

## 6. Conclusion

The ISMS continues to be suitable, adequate, and effective. The two open minor
nonconformities are understood, owned, and on track for closure before Stage 1. The
management team approved the certification application and the resources required for
the audit period.

## 7. Next meeting

July 2027, with a focus on Stage 1 results, NC closure, EDR rollout, and the Series B
security due diligence preparation.

## 8. Sign-off

| Role | Name | Date |
|---|---|---|
| Chair | Karim Salah | 29 April 2027 |
| Minutes | ISMS Manager | 29 April 2027 |

## 9. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 29 April 2027 | Initial management review minutes | ISMS Manager |
