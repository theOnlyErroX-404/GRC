# Penetration Test Summary

| Field | Value |
|---|---|
| Document ID | NH-SEC-001 |
| Test window | 8–19 March 2027 |
| Report date | 22 March 2027 |
| Tester | NileSec Security Consultants (simulated) |
| Owner | Omar Nasser, CTO |
| Classification | Internal (simulated client confidential) |

> **Simulation notice:** Nabd Health is fictional. This summary is part of a simulated
> ISO/IEC 27001:2022 implementation and does not describe a real organization. The
> tester and findings are invented.

## 1. Scope

| Target | Type |
|---|---|
| Patient web application and API | External, authenticated and unauthenticated |
| Patient mobile app (iOS and Android) | External, API and client-side review |
| Admin Panel | External, authenticated with test accounts |
| AWS configuration | Configuration review of production and non-production accounts |
| Authentication and session management | Manual and automated testing |
| Rate limiting and abuse cases | OTP, login, booking, export |

Out of scope: denial-of-service testing, social engineering, Pixelwave premises, and
supplier infrastructure other than configuration shared with Nabd.

## 2. Method

The test followed a black-box and grey-box approach using OWASP WSTG and MASVS. Test
accounts were provided for clinic staff, patient, and support roles. Testing was
performed from the internet and from an approved VPN address. No production data was
exfiltrated; evidence was minimized and shared through an encrypted portal.

## 3. Findings summary

| Severity | Count | Remediated before report | Open at report |
|---|---|---|---|
| Critical | 0 | 0 | 0 |
| High | 1 | 1 | 0 |
| Medium | 2 | 2 | 0 |
| Low | 4 | 3 | 1 accepted |
| Informational | 3 | N/A | N/A |

## 4. High finding

### PT-01: Broken object-level authorization in appointment metadata

**Affected:** `GET /api/v1/appointments/{id}` for authenticated clinic staff.

**Description:** A staff user from one clinic could request an appointment identifier
belonging to another clinic and receive appointment metadata (time, clinic name, doctor
identifier, status). Patient clinical notes and files were not exposed. The tenant check
was applied in the UI but not enforced consistently in the service layer.

**Impact:** Cross-tenant disclosure of limited appointment metadata. A malicious clinic
user could enumerate identifiers and infer activity at another clinic.

**Remediation:** The API now enforces clinic ID from the authenticated session on every
appointment query, with a centralized authorization check and a regression test.
Deployed on 16 March 2027.

**Retest:** 24 March 2027; not exploitable. Evidence retained.

## 5. Medium findings

| ID | Finding | Remediation | Status |
|---|---|---|---|
| PT-02 | OTP verification endpoint lacked per-account rate limiting, allowing repeated attempts within the code validity window | Per-account and per-IP limits added; lockout after five failures; monitoring alert | Fixed and retested |
| PT-03 | Verbose error responses exposed stack traces and framework versions on two API endpoints | Error handling standardized; details removed from responses; logs retain correlation ID | Fixed and retested |

## 6. Low findings

| ID | Finding | Status |
|---|---|---|
| PT-04 | Session cookie missing `SameSite=Strict` on one legacy admin route | Fixed |
| PT-05 | TLS 1.2 cipher suite included a legacy CBC option | Fixed; TLS 1.3 preferred |
| PT-06 | Server banner disclosed nginx version | Fixed |
| PT-07 | Password reset response timing differed slightly for valid and invalid accounts | Accepted; low risk and mitigating rate limits; review in 2028 |

## 7. Informational observations

- Add security headers (CSP, HSTS preload) to the marketing site when it is next changed.
- Consider passkeys for clinic administrators to reduce phishing risk further.
- Add automated authorization tests to CI for every new API endpoint.

## 8. Conclusion

No critical vulnerabilities were found. The single high finding was remediated and
retested. The test provides reasonable assurance that the external attack surface is
managed, and the results support the treatment of R-09 and the effectiveness of A.8.29.
Findings were tracked to closure in the vulnerability register.

## 9. Sign-off

| Role | Name | Date |
|---|---|---|
| Lead tester | NileSec (simulated) | 22 March 2027 |
| Nabd owner | Omar Nasser | 24 March 2027 |
| Retest | NileSec | 24 March 2027 |
