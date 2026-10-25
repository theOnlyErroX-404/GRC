# Backup Restore Test Record

| Field | Value |
|---|---|
| Document ID | NH-PRC-004 |
| Version | 1.0 |
| Status | Completed |
| Test date | 14 March 2027 |
| Owner | Ahmed Rizk, DevOps Lead |
| Approved by | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This record is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This record documents the quarterly restoration test required by NH-POL-008. It proves
that backups can be restored within the approved RPO and RTO and that restored data is
usable.

## 2. Test scope

| Item | Detail |
|---|---|
| Test ID | BRT-2027-Q1 |
| Test type | Partial restore into an isolated environment |
| Systems tested | RDS PostgreSQL production snapshot, S3 patient files, Terraform state |
| Backup source | Automated snapshot of 13 March 2027 23:00 UTC; S3 versioning; state bucket version |
| Restore target | Isolated VPC and temporary AWS account `nabd-restore-test` |
| Data handling | Restored data encrypted; access limited to DevOps Lead and CTO; environment destroyed after validation |
| Participants | Ahmed Rizk (DevOps Lead), Omar Nasser (CTO), Sara Lotfy (Engineering Manager) |
| Objective | RPO 1 hour, RTO 4 hours for RDS and 8 hours for S3 |

## 3. Procedure

1. Confirm the backup completion status and checksum.
2. Create an isolated VPC and temporary account with no route to production.
3. Restore the RDS snapshot to a new instance with the same engine version.
4. Restore a random sample of 25 patient files from S3 versioning.
5. Restore the Terraform state version and verify checksum.
6. Run integrity checks: row counts, referential integrity, file hashes, application
   smoke test with synthetic credentials.
7. Measure elapsed time from restore start to validated service.
8. Record issues, destroy the environment, and confirm deletion.

## 4. Results

| Check | Expected | Actual | Result |
|---|---|---|---|
| RDS snapshot completion | Successful | Successful, 23:12 UTC | Pass |
| RDS restore time | Under 4 hours | 2 hours 18 minutes | Pass |
| RPO achieved | 1 hour or less | 42 minutes (backup at 23:00, test point 23:42) | Pass |
| Row count: patients | 412,000 | 411,986 | Pass with variance |
| Row count: visit notes | About 2.8 million | 2,798,441 | Pass |
| Referential integrity | No orphan records | 0 orphans | Pass |
| S3 sample restore | 25 of 25 files | 25 of 25, hashes match | Pass |
| S3 restore time | Under 8 hours | 3 hours 5 minutes | Pass |
| Terraform state restore | Version and checksum match | Match | Pass |
| Application smoke test | Login, booking, record view | All passed with synthetic account | Pass |
| Tenant isolation check | No cross-tenant data | No cross-tenant data observed | Pass |
| Encryption at rest | Enabled | Enabled on restored volumes | Pass |
| Environment deletion | Complete | Confirmed; temporary account closed | Pass |

## 5. Observations

1. The patient row count differs from the reported figure by 14 records. The difference
   is explained by clinic deletions on the morning of 14 March 2027, after the backup
   point. No action required; the test record notes the reconciliation.
2. RDS restoration was faster than the previous test because the snapshot was in the same
   region. Cross-region restoration has not yet been tested and is scheduled for Q2 2027.
3. S3 restoration required manual selection of versions for 3 files. A scripted restore
   procedure is being written to reduce error.
4. The temporary account lacked the standard guardrails at creation. The DevOps Lead
   added a budget and region restriction during the test. The account baseline will be
   added to the restore runbook.

## 6. Actions

| Action | Owner | Due | Status |
|---|---|---|---|
| Test cross-region restore for RDS and S3 | DevOps Lead | 2027-06-15 | Open |
| Automate S3 version selection and restore | DevOps Lead | 2027-05-15 | Open |
| Add temporary restore account baseline to the runbook | DevOps Lead | 2027-04-15 | Complete |
| Reconcile backup row counts with the data warehouse daily | Engineering Manager | 2027-04-30 | Open |

## 7. Conclusion

The test demonstrates that Priority 1 data can be restored within the approved RTO and
RPO in the primary region. Cross-region recovery remains to be proven and is tracked as
an open action under risk R-03. The next test is scheduled for 14 June 2027.

## 8. Sign-off

| Role | Name | Date |
|---|---|---|
| Test lead | Ahmed Rizk | 14 March 2027 |
| Approver | Omar Nasser | 15 March 2027 |
| Witness | Sara Lotfy | 14 March 2027 |

## 9. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 15 March 2027 | Initial test record | DevOps Lead |
