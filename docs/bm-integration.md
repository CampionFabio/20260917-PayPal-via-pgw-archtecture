# BM Integration

Payment integration into BM for STO orders is currently done via the **AzureBookmasterRelay**
application.

## Payment reference field

STO payment details include a field named **`BankReference1`**. When an order is paid via
voucher, STO populates `BankReference1` with the voucher number. For PayPal payments, this field
will instead be populated with the **PayPal transaction number**.

## New payment type

BM must support a new payment type: **PayPal**. BM must add this payment type as part of the
payment details for each order. This payment type must be separate from existing payment types,
such as credit card and voucher.

## Current behaviour: multiple orders per cart

STO allows multiple orders to be presented to the user and visually grouped into a single total.
However, when processing payment, STO currently processes **individual payments per order** even
though the user only sees one combined total.

## Problem with PayPal and multiple orders

Processing individual PayPal payments per order would require the end user to go through the
PayPal payment screen once per order (e.g. 3 times for 3 orders in the cart). This is not an
acceptable user experience.

## Proposed implementation

- Process a **single PayPal payment** for the **sum total of all orders** in the cart.
- Sync the **same PayPal transaction number** into the `BankReference1` field in BM for **each
  individual order** in that cart.

## Constraint: no changes to AzureBookmasterRelay

The team must not change the AzureBookmasterRelay application. The team must implement the
proposed solution without changes to this application.

## Risks

- BM currently uses the `BankReference1` field for vouchers. Specific customizations in BM link
  to this field for voucher processing. These customizations may not work with PayPal
  transaction numbers in this field.
- The team must build a small proof of concept (POC). The POC must send the proposed data into
  BM. The team must observe the results before the team approves this design.
