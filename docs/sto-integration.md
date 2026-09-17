# STO Integration

## Current behaviour

STO creates and groups orders into a checkout page. The user places items into a cart. STO
translates each cart into a separate order.

STO processes payment for each order as a separate transaction. STO sends each transaction to:

1. **PGW** — for payment processing.
2. **BM** — for payment data update.

## Proposed changes

STO must let the user choose a payment method. The user must choose between:

1. **Existing credit card payment via PGW**.
2. **PayPal**.

### Existing credit card payment

If the user chooses credit card payment, the checkout workflow must stay the same as the current
workflow, for all remaining pages.

### PayPal payment

If the user chooses PayPal, a new workflow must take place.

> More details about the new PayPal workflow will follow.
