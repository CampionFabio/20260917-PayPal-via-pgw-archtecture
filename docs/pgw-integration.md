# PGW Integration

## Current behaviour

PGW currently handles the creation of credit card (CC) tokens. PGW currently processes payments
and refunds using these tokens via **MPGS (Mastercard Payment Gateway System)**.

## Proposed changes

PGW must support PayPal Pay in 4 with business rules analogous to the business rules it applies
to MPGS today, for token creation, payment capture, and refunds. These rules cannot be the same
rules as the MPGS rules, because PayPal Pay in 4 follows a slightly different workflow than MPGS
when it processes a payment.

PGW must have a new structure to save the PayPal business credentials. PGW will use this
structure to authenticate PayPal Pay in 4 workflows.

## Constraint: no interference with MPGS

The PayPal implementation must not interfere with payment processing via MPGS. MPGS payment
processing must continue to work as it works today.

> Technical details will follow.
