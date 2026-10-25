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
| 01 | [Nabd Health](projects/01-nabd-health-isms/) | Digital health SaaS — Egypt | ISO/IEC 27001:2022 ISMS: gap analysis → risk register → SoA → internal audit → certification readiness | Simulated implementation complete; Stage 1 planned June 2027 |

## Project 01 — Nabd Health

Nabd Health for Digital Health Solutions S.A.E. is a fictional 60-person Egyptian
company providing appointment booking, electronic patient records, telemedicine, and
billing to private clinics and small hospitals. The simulated engagement is a full
ISO/IEC 27001:2022 ISMS implementation covering the Cairo office, remote working, and
the AWS production and non-production environments.

The project starts from a 22-gap baseline and works through scope, leadership, risk
assessment, treatment, a 93-control Statement of Applicability, 14 policies, operational
procedures and evidence, an independent internal audit, and management review. Every
artifact traces back to the company fact base.

**Start here:** [Project document index](projects/01-nabd-health-isms/README.md)

## Standards and frameworks

ISO/IEC 27001:2022 (including Amendment 1:2024) · NIST CSF 2.0 · SOC 2 ·
Egyptian PDPL (Law 151/2020)

## Repository layout

```
projects/
  01-nabd-health-isms/
    README.md                     Project overview and document index
    00-company-fact-base.md       Single source of truth for the fictional company
    01-context/                   Context, interested parties, ISMS scope
    02-leadership/                Information security policy, roles and RACI
    03-risk/                      Methodology, asset register, risk register,
                                  treatment plan, Statement of Applicability
    04-policies/                  13 topic-specific policies
    05-operation/                 Procedures, incident response, BCP/DR,
                                  supplier register, evidence index
    06-performance/               KPIs, internal audit plan and report,
                                  management review minutes
    07-improvement/               Nonconformity and corrective action log
    diagrams/                     Architecture and ISMS process maps
```
