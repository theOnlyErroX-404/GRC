# GRC — Simulated Governance, Risk & Compliance Projects

A portfolio of GRC work built end to end against fictional organizations. Each project
follows the full lifecycle — discovery, scoping, risk assessment, control design,
evidence, audit, and reporting — and produces the artifacts a real engagement would.

> **Everything here is fictional.** Companies, people, systems, suppliers, incidents,
> and data are invented. Nothing in this repository describes a real client, employer,
> or certification. Any resemblance to a real organization is coincidental.

---

## Projects

| # | Company | Sector | Focus | Status |
|---|---|---|---|---|
| 01 | Nabd Health | Digital health SaaS — Egypt | ISO/IEC 27001:2022 ISMS: gap analysis → risk register → SoA → internal audit → certification readiness | In progress |

## Project 01 — Nabd Health

Nabd Health for Digital Health Solutions S.A.E. is a fictional 60-person Egyptian
company providing appointment booking, electronic patient records, telemedicine, and
billing to private clinics and small hospitals. The simulated engagement is a full
ISO/IEC 27001:2022 ISMS implementation covering the Cairo office, remote working, and
the AWS production and non-production environments.

All work traces to a single source of truth: a company fact base that fixes the
organization's people, systems, suppliers, data, and 22 known baseline gaps. Every
asset, risk, Statement of Applicability entry, and audit finding references that
baseline.

## Standards and frameworks

ISO/IEC 27001:2022 (including Amendment 1:2024) · NIST CSF 2.0 · SOC 2 ·
Egyptian PDPL (Law 151/2020)

## Repository layout

Each project is self-contained: a company fact base followed by context, leadership,
risk, policies, operation, performance, and improvement artifacts.

```
projects/
  01-nabd-health-isms/
    00-company-fact-base.md
    01-context/
    02-leadership/
    03-risk/
    04-policies/
    05-operation/
    06-performance/
    07-improvement/
```
