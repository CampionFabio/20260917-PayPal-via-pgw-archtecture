# PayPal via PGW Architecture

This repository contains the documents and diagrams for the implementation of **PayPal** payment
integration into **PGW (Payment Gateway Wrapper)**.

PGW is the system used by Campion Education as the central component for processing credit card
payments. This project documents the architecture, design decisions, and diagrams required to add
PayPal as a supported payment method alongside existing credit card processing.

## Systems Involved

- **STO (Student Ordering)** — the system where payments are captured (checkout/order flow
  initiating PayPal payments).
- **PGW (Payment Gateway Wrapper)** — the central payment processing system into which PayPal is
  being integrated as a payment method.
- **BM (Bookmaster)** — payment captures and refunds must be synchronised into BM.
- **AzureBookmasterRelay** — the application that sends payment data from STO into BM.
- **W4P (Web for Point of Sale)** — refunds are processed via W4P.
- **PayPal** — the new payment method being integrated.

## Documents

- [PGW Integration](./docs/pgw-integration.md) — new PayPal token/credential structure in PGW,
  and the constraint to not interfere with MPGS processing.
- [W4P Integration](./docs/w4p-integration.md) — how W4P refund pages must support PayPal
  orders.
- [PayPal Integration](./docs/paypal-integration.md) — PayPal Business Account setup, and PayPal
  workflows and technical details.
- [STO Integration](./docs/sto-integration.md) — how STO must let the user choose a payment
  method, and the checkout changes needed for PayPal.
- [BM Integration](./docs/bm-integration.md) — how PayPal payment captures and refunds are
  synchronised into Bookmaster via AzureBookmasterRelay.

## Status

This repository is currently a placeholder. Content will be added incrementally as the
architecture and implementation are defined.

## Contents

- `docs/` — architecture documents, decisions, and specifications
- `diagrams/` — architecture and sequence diagrams (to be added)

## Contributing

See [AGENTS.md](./AGENTS.md) for conventions and guidance when working in this repository,
including with AI coding agents.
