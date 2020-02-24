# care giver payments

The Care Giver Payments component is responsible for managing financial transactions to care givers mediated by the platform.

The component will interface with the following 'external' systems:

* payment service: initiating payment transactions
* eccoo accounting system: reconciliation of transactions

## Critical requirements

More detail is required on the business design of processes surrounding payment to define the data that is required to be managed.

* Must be possible to initiate a payment to a care givers registered bank details
* Must use the stored data about the care transactions from the care log to determine the payment
* Should be possible to reconcile transactions with the eccoo bank payments \(for accounting purposes\)

## Implementation

This is likely to be another implementation of Ledger DB technology to manage the transactions in and out of the various accounts / pots.

## Invoicing

* Individual to individual - what is the need for an invoice?
  * Receipt may be required to reclaim
  * Some cases - e.g. accountant managed funds - needs invoice in arrears to pay. Largish proportion \(1 out of 9 on current pilot with a some new extras\).

### Taking Payment

Methods of payment

Payment partner?

### Making Payment

Payment partner?

Reconciliation with eccoo bank / accounting

### References

[https://stripe.com/gb/connect](https://stripe.com/gb/connect)

