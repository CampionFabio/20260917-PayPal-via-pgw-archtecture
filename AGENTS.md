# Agent Instructions

This repository is a **documentation and architecture** project, not a software codebase. Its
purpose is to design and document the integration of PayPal as a payment method into PGW (Payment
Gateway Wrapper), the system Campion Education uses to process credit card payments.

## Scope

- This repo produces documents (Markdown, etc.) and diagrams (e.g. Mermaid, draw.io, PlantUML)
  describing the PayPal-via-PGW architecture, decisions, and integration flows.
- There is no application source code, build, or test suite here. Do not introduce one unless
  explicitly asked.

## Conventions

- Keep documents in `docs/` and diagrams in `diagrams/` (create these folders as content is
  added).
- Prefer diagrams-as-code (e.g. Mermaid) so diagrams are diffable in version control.
- Use clear, descriptive filenames in kebab-case (e.g. `paypal-checkout-sequence.md`).
- Keep documents concise and structured (headings, bullet points) so they are easy to review.
- Write all document text using **ASD-STE100 Simplified Technical English (STE)**: short
  sentences, one instruction per sentence, active voice, approved words used consistently, and
  avoidance of jargon, idioms, and ambiguous phrasing.

## Working in this repo

- This is a placeholder stage — structure and content will evolve. Confirm scope with the user
  before creating large amounts of new documentation.
- Do not fabricate technical details about PGW or PayPal internals; ask the user for
  clarification when details are unknown.
- When adding diagrams, briefly explain what they represent alongside the file.
