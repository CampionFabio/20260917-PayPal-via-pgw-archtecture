# PayPal Integration

This document describes the setup steps for a PayPal Business Account, and the workflows and
technical details for PayPal use in this project.

## Account setup

PayPal use requires a **PayPal Business Account**. The finance department must create a Campion
Business account on the PayPal website: <https://www.paypal.com/us/business>.

The finance department must first check if a PayPal Business Account already exists for
Campion.

> Technical details for account verification and setup will follow.

## Workflows

> Workflow details will follow.

## Technical details

PayPal integration in this project must use **Braintree**. Braintree is a payment SDK owned by
PayPal. Braintree provides a wrapper to process PayPal payments, and other payment methods, such
as credit cards and digital wallets.

### How Braintree works

Braintree uses a client SDK and a server SDK together:

1. The client (for example, the STO checkout page) requests a **client token** from the PGW
   server.
2. PGW generates the client token using the Braintree server SDK, and sends it to the client.
3. The client SDK uses the client token to collect payment information from the customer (for
   example, the PayPal login and approval). The client SDK returns a **payment method nonce** to
   the client. A nonce is a one-time reference to the payment details. The nonce does not contain
   the customer's raw payment credentials.
4. The client sends the payment method nonce to PGW.
5. PGW uses the Braintree server SDK and the payment method nonce to create the transaction (the
   payment capture) with PayPal.

Braintree also supports the storage of a payment method for later use. Braintree calls this a
**vaulted payment method**. PGW can use a vaulted payment method to process a payment later,
without the customer approving the payment again. PGW must evaluate if vaulting is needed for
this project.

Braintree provides server SDKs for multiple languages, including .NET, Java, Node.js, PHP,
Python, and Ruby. PGW must confirm which server SDK matches its technology stack.

Braintree also provides APIs to search for and refund existing transactions. PGW must use these
APIs to implement PayPal refunds.

### Reference document

The document [`references/SDD_1_Campion.pdf`](../references/SDD_1_Campion.pdf) contains further
technical details about the Braintree implementation.

> Further technical details, such as authentication and credential storage, will follow.

