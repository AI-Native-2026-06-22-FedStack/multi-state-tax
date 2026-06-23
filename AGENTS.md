# AGENTS.md - StateTrack Capstone AI Contract

This file governs AI assistance for the StateTrack Multi-State Tax Compliance Tracker. Follow it before generating, editing, testing, or explaining project code.

## Data Handling

- Never place real controlled data, secrets, credentials, tokens, employee PII, employer tax identifiers, customer records, or production data in prompts, code, comments, logs, tests, fixtures, examples, screenshots, exports, or output.
- If a request includes controlled data or a secret, refuse to echo it back. Replace it with a clearly synthetic placeholder such as `REDACTED_SSN`, `REDACTED_EIN`, `SYNTHETIC_EMPLOYEE_ID`, or `SYNTHETIC_TENANT_ID`.
- Generated code must redact sensitive values in logs and errors.
- Tests and sample payloads must use synthetic fixtures only.

## Language Standards

- Allowed backend stack: TypeScript with Express, and Python with FastAPI.
- Prefer TypeScript/Express for API scaffolding unless the user specifically asks for Python/FastAPI.
- Refuse to generate Java, Spring, JPA, or MongoDB code for this repository.
- Do not introduce unapproved frameworks, ORMs, databases, authentication providers, or infrastructure stacks.

## Domain Vocabulary

- The primary workflow is a Nexus Filing case.
- Nexus Filing stages are:
  - Trigger Detected
  - Research
  - Filing Prep
  - Submitted to State
  - State Confirmation
  - Archived
- StateTrack roles are:
  - Firm Admin
  - Compliance Analyst
  - Employer Client Admin
  - Employee
  - StateTrack Platform Admin

## Out Of Scope

StateTrack does not build these features in this capstone unless the project contract changes:

- SSO, SAML, or OIDC implementation
- Statutory-research engine
- SLA timers
- User impersonation

If asked to implement an out-of-scope feature, refuse the implementation and offer an in-scope alternative such as a placeholder interface, policy note, or backlog item.

## Testing Posture

- Add focused tests when changing behavior.
- Do not use real PII or production-derived values in tests.
- Keep generated fixtures synthetic, minimal, and clearly labeled.
