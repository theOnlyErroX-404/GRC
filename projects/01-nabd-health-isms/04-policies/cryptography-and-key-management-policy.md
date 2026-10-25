# Cryptography and Key Management Policy

| Field | Value |
|---|---|
| Document ID | NH-POL-014 |
| Version | 1.0 |
| Status | Approved |
| Simulation date | 26 February 2027 |
| Owner | Omar Nasser, CTO |
| Approved by | Karim Salah, CEO |
| Classification | Internal (simulated client confidential) |
| Next review | February 2028 |

> **Simulation notice:** Nabd Health is fictional. This policy is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization.

## 1. Purpose

This policy defines how Nabd Health uses cryptography to protect information in transit,
at rest, and in use, and how cryptographic keys and secrets are managed. It implements
Annex A control A.8.24 and supports A.5.14 and A.8.5.

## 2. Scope

Applies to all systems, applications, devices, backups, and data flows within the ISMS
scope, including customer data, employee data, source code, and secrets.

## 3. Cryptographic standards

| Use | Standard |
|---|---|
| Transport encryption | TLS 1.2 minimum; TLS 1.3 preferred; strong cipher suites only |
| Data at rest | AES-256 or provider equivalent |
| Password storage | bcrypt with cost factor at least 12, or Argon2id |
| Hashing and integrity | SHA-256 or stronger |
| Key exchange | ECDHE with approved curves |
| Certificates | Publicly trusted CA or AWS Certificate Manager; auto-renewal |
| Random values | Cryptographically secure random number generator |
| OTP | Six digits, 10-minute validity, single use, rate limited |

MD5, SHA-1, DES, 3DES, RC4, and TLS 1.0/1.1 are prohibited. Legacy exceptions require
CTO approval and a remediation date.

## 4. Data protection

1. Patient data is encrypted in transit over all external and internal networks.
2. RDS, S3, backups, and snapshots are encrypted at rest. The preferred approach is a
   customer-managed KMS key; where AWS-managed keys are used, the rationale is recorded.
3. No patient data is stored on endpoints without encryption.
4. Application-level field encryption is required for highly sensitive fields where the
   data store cannot provide sufficient separation of duties.
5. Data in use protections (masking, tokenization) are applied to staging and analytics
   where full records are not required.
6. Payment card data is not stored by Nabd; PayNile handles card data.

## 5. Key management

| Key type | Storage | Rotation | Access |
|---|---|---|---|
| AWS KMS keys | AWS KMS | Annual or on compromise | CTO and DevOps Lead via IAM |
| TLS certificates | AWS Certificate Manager | Automatic | DevOps Lead |
| Application secrets | AWS Secrets Manager | 90 days or on change | Application roles and DevOps |
| CI/CD secrets | GitHub OIDC preferred; Secrets Manager otherwise | 90 days | Engineering Manager |
| SSH host and user keys | Per-person certificates; host keys pinned | Annual or on change | DevOps Lead |
| Backup encryption keys | AWS KMS | Annual | CTO and DevOps Lead |
| Password manager vault | Company password manager | On compromise | Users and CTO |
| Mobile signing keys | Hardware-backed store | On change or staff departure | Two named engineers |

Key ceremonies, where used, require two people. Private keys must never be shared,
exported, or stored in source code. Compromised keys are revoked immediately and the
incident process is followed.

## 6. Secrets management

- Secrets are stored in AWS Secrets Manager or the password manager, never in code,
  tickets, documents, or chat.
- Applications retrieve secrets at runtime using IAM roles.
- GitHub Actions uses OIDC federation instead of long-lived cloud keys.
- Secret scanning and push protection are enabled on all repositories.
- Access to secrets is logged and reviewed quarterly.
- Leaked secrets are rotated immediately and investigated as an incident.

## 7. Certificate management

Certificates are issued through AWS Certificate Manager or a trusted public CA.
Expiry is monitored, renewal is automated where possible, and an alert is raised 30 days
before expiry. Certificates using weak algorithms or expired certificates are removed
from service.

## 8. Cryptographic change and agility

The CTO reviews cryptographic standards at least annually and when a significant
vulnerability or regulatory requirement emerges. Systems must be able to rotate keys and
replace algorithms without redesigning the application. Deprecated algorithms are
tracked in the vulnerability management process.

## 9. Roles

| Role | Responsibility |
|---|---|
| CTO | Approves standards, key management, and exceptions |
| DevOps Lead | Operates KMS, certificates, secrets, and rotation |
| Engineering Manager | Ensures applications use approved libraries and patterns |
| All staff | Protect credentials and report suspected compromise |

## 10. Related documents

- NH-POL-002 Access Control Policy
- NH-POL-003 Acceptable Use and Information Handling Policy
- NH-POL-009 Secure Development and Change Management Policy
- NH-POL-010 Vulnerability and Configuration Management Policy
- NH-POL-012 Logging and Monitoring Policy

## 11. Revision history

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | 26 February 2027 | Initial cryptography and key management policy | ISMS Lead Implementer |
