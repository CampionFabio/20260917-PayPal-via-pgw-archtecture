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
- **W4P (Web for Point of Sale)** — refunds are processed via W4P.
- **PayPal** — the new payment method being integrated.

## Status

This repository is currently a placeholder. Content will be added incrementally as the
architecture and implementation are defined.

## Contents

- `docs/` — architecture documents, decisions, and specifications (to be added)
- `diagrams/` — architecture and sequence diagrams (to be added)

## Contributing

See [AGENTS.md](./AGENTS.md) for conventions and guidance when working in this repository,
including with AI coding agents.
