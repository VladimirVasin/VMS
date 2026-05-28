# AGENTS

This repository is used as shared AI/context memory for the AvidSys/VMS project.

## Read Order

1. Read `ai/README.md`.
2. Read `ai/final-project-overview-2026-05-28.md`.
3. Read `ai/programs-enrollment-process-overview.md` for detailed Programs&Enrollment context.
4. Read `ai/azure-feature-24497-programs-enrollment.md` when exact Azure DevOps story text is needed.

## Rules

- Treat source systems and live code as source of truth if they disagree with memory.
- Keep memory concise and factual.
- Do not paste secrets, tokens, production credentials, private customer data, or browser session data.
- When adding new Azure DevOps context, include IDs, titles, states, source URLs, and capture date.
- Prefer stable process summaries in separate files instead of expanding `README.md`.
- In final QA/testing reports, always include direct links to every record that participated in the test: source Azure DevOps item, created/updated Dynamics records, generated child records, reference/configuration records used for expected results, and any important list/view used for verification.
