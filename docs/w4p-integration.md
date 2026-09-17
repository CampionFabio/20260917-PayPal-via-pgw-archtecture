# W4P Integration

## Current behaviour

W4P centralises payment refunds. Staff use W4P to process refunds for orders.

## Proposed changes

The payment refund pages in W4P must change. The adjusted pages must allow refunds of PayPal
orders.

Refunds of PayPal orders must follow the existing business rules for when orders can be
refunded.

> Technical details will follow.

## Risks

- Evaluation of refund workflows for **PayPal Pay Later** orders is pending. PayPal Pay Later is
  a payment plan, so a refund may affect the customer's remaining installments in a different way
  than a standard PayPal refund. Confirmation of the refund behaviour with PayPal is pending
  before W4P implementation.
