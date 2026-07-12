# Data Classification & Federal Posture

## Buckets

- PUBLIC: Information approved for public release or harmless synthetic data created only for examples, tests, and demos. PUBLIC and synthetic data may enter prompts.
- CUI: Controlled Unclassified Information that requires safeguarding or dissemination controls. Real CUI must never enter prompts, generated output, examples, tests, logs, or exported samples.
- SBU: Sensitive But Unclassified information. Treat SBU at least as strictly as CUI for this project. Real SBU must never enter prompts or generated artifacts.

## The Bright Line

Synthetic data and PUBLIC data may enter a prompt. Real CUI, SBU, secrets, credentials, tokens, production records, customer records, employee PII, and employer tax identifiers must never enter a prompt.

If sensitive data appears in a request, the AI response must not repeat it. The response should replace it with a synthetic placeholder such as `REDACTED_SSN`, `REDACTED_EIN`, or `SYNTHETIC_VALUE`.

## StateTrack Sensitive Fields

- Employee SSN is sensitive PII.
- Employer EIN is sensitive PII and tax-identifying data.
- SSN and EIN values must be redacted in logs, errors, support traces, analytics, screenshots, and generated output.
- SSN and EIN values must never appear in event payloads, exported samples, seeded fixtures, demo data, or tests.
- Event payloads may carry opaque internal identifiers only when those identifiers are synthetic in local examples and do not expose sensitive source values.

## Obligations For Later Sprints

- Enforce per-tenant data isolation so one employer, firm, or user cannot access another tenant's cases, employee records, filings, or audit events.
- Apply least privilege by role: Firm Admin, Compliance Analyst, Employer Client Admin, Employee, and StateTrack Platform Admin must receive only the access required for their workflow.
- Keep audit events useful without recording sensitive values.
- Validate exports and sample files so they contain no real SSN, EIN, CUI, SBU, credentials, or production-derived data.
