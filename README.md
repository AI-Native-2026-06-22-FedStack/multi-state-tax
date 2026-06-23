# Govern the AI Before You Code: Bootstrap the StateTrack Repo

StateTrack is a capstone repository for a Multi-State Tax Compliance Tracker. This repository starts with the governance layer first: Codex behavior, the project AI contract, data-classification posture, guardrail evidence, and a prompt journal.

## Clean-clone setup

1. Clone the private repository.

   ```bash
   git clone <your-github-repo-url>
   cd multi-state-tax
   ```

2. Create or switch to the Deliverable 1 branch.

   ```bash
   git checkout -b m1d1-implementation main
   ```

3. Confirm the governance artifacts are present.

   ```bash
   test -f config.toml
   test -f AGENTS.md
   test -f docs/data-classification.md
   test -f evidence/guardrails-check.md
   test -f prompt-journal/0001-bootstrap.md
   ```

4. Start Codex from the repository root so it reads the root-level contract and uses the repository configuration.

   ```bash
   codex
   ```

5. Before requesting or accepting feature code, review the project guardrails:

   - [AGENTS.md](AGENTS.md) defines the StateTrack AI contract.
   - [docs/data-classification.md](docs/data-classification.md) defines the data-classification posture.
   - [evidence/guardrails-check.md](evidence/guardrails-check.md) records the initial guardrail proof.
   - [prompt-journal/0001-bootstrap.md](prompt-journal/0001-bootstrap.md) records the first AI interaction decision.

## Prompt journal format

The user decides when a journal note should be created. When asked to add one, use the format defined in [AGENTS.md](AGENTS.md): `Asked`, `Produced`, `Accepted / Rejected`, and `Why`.

## Guardrail self-check

Run this from the repository root before submitting the PR:

```bash
test -f config.toml &&
test -f AGENTS.md &&
test -f docs/data-classification.md &&
test -f evidence/guardrails-check.md &&
test -f prompt-journal/0001-bootstrap.md &&
grep -q "AGENTS.md" README.md &&
grep -q "data-classification.md" README.md &&
grep -q "workspace-write" config.toml &&
grep -q 'model_reasoning_effort = "low"' config.toml &&
grep -q "on-request" config.toml &&
grep -q "TypeScript" AGENTS.md &&
grep -q "FastAPI" AGENTS.md &&
grep -q "Prompt Journal" AGENTS.md &&
grep -q "SSN" docs/data-classification.md &&
grep -q "EIN" docs/data-classification.md &&
grep -q "Risky action" evidence/guardrails-check.md &&
grep -q "Asked" prompt-journal/0001-bootstrap.md &&
echo "PASS: governance artifacts present, referenced, and proven"
```
