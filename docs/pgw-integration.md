# PGW Integration

## Current behaviour

PGW currently handles the creation of credit card (CC) tokens. PGW currently processes payments
and refunds using these tokens via **MPGS (Mastercard Payment Gateway System)**.

## Proposed changes

PGW must apply business rules to PayPal analogous to the business rules it applies to MPGS
today. These rules cannot be the same rules, because PayPal follows a slightly different
workflow than MPGS when it processes a payment. PGW must support token creation, payment
capture, and refunds for PayPal, based on the same rules it uses for MPGS.

PGW must have a new structure to save PayPal credentials. PGW must use this structure to process
PayPal payments and refunds.

## Constraint: no interference with MPGS

The PayPal implementation must not interfere with payment processing via MPGS. MPGS payment
processing must continue to work as it works today.

> Technical details will follow.
