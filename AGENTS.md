# Project Guidelines — tax-engine (Public Open Source)

## 1. Absolute Privacy & Zero-Leak Invariant (NON-NEGOTIABLE)
- This is a 100% public open-source repository.
- NEVER commit, stage, reference, or hardcode personal identities, real names, real tax IDs (IdNr, Steuernummer), real addresses, banking coordinates, or real financial figures.
- NEVER hardcode machine-specific paths (such as local home directory paths) or links to private repositories.
- NEVER commit credentials, private keys, ELSTER certificate files (`.pfx`), or passwords.
- Any test fixtures or sample payloads MUST strictly use standard RFC dummy data:
  - Name: "Max Mustermann" / "Erika Musterfrau"
  - Tax ID: "04444444441" (official ELSTER test IdNr)
  - Steuernummer: "9181081508155" (official ELSTER test Steuernummer)
  - Employer: "Musterfirma GmbH"

## 2. Decoupled Architecture & Pluggable Data Provider
- The core tax calculation and transmission engine is data-source agnostic.
- It operates strictly via abstract protocols and interfaces (such as `TaxDataProvider`).
- It must never take a direct dependency on private database schemas, private financial tools, or proprietary cloud storage.
- External systems connect via standard JSON, YAML, or in-memory dictionary payloads.

## 3. Cognitive Accessibility (Barrierefreiheit / BFSG)
- All CLI outputs, diagnostics, and step-by-step guidance must prioritize cognitive accessibility:
  - Plain-language validation errors explaining what is missing or incorrect, rather than cryptic tax code numbers.
  - Number abstraction and structured breakdowns instead of dense, unformatted tabular data.
  - Step-by-step interactive verification rather than monolithic form dumps.

## 4. Quality & Statutory Verification
- Full test coverage for statutory calculation rules.
- Every statutory constant must reference its official legal citation (§ EStG or BMF circular).
- Pre-commit hygiene ensures no private tokens, machine paths, or unapproved test identifiers are committed.
