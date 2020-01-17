# payments

The Payments component is responsible for managing financial transactions mediated by the platform. Initially this will include payments by and to platform users, but will extend to managing financial 'pots' which might contain funds from Local Authorities, NHS or other sources.

The payments will interface with the following 'external' systems:

* payment service: initiating payment transactions
* eccoo accounting system: reconciliation of transactions

## Critical requirements

More detail is required on the processes surrounding payment to define the data that is required to be managed.

* Must be possible to create invoices \(required for reclaims / payments\)
* Must be able to track multiple different types of accounts based on platform user role
  * outgoing payment account for care givers
  * incoming payment account for care receivers
  * managed fund account\(s\) for care receivers 
  * care coins account for any user

## Implementation

This is likely to be another implementation of Ledger DB technology to manage the transactions in and out of the various accounts / pots.

## Reference

### Regulation

It is possible that eccoo will be subject to financial regulation as it aspires to manage and distribute funds on behalf of end users. Even in the initial iteration, the management of funds transfers between care receivers and care givers may have

The Financial Conduct Authority is the UK body which managed regulation and authorisation of companies engaged in financial activities.

The following references may help clarify the requirement. It is worth undertaking due diligence, perhaps by contacting the FCA in an advisory capacity.

{% embed url="https://www.fca.org.uk/firms/authorisation/how-to-apply/activities" caption="" %}

The FCA handbook may define what eccoo are doing as a Payment Account.

{% embed url="https://www.handbook.fca.org.uk/handbook/PERG/15/3.html" caption="" %}

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

