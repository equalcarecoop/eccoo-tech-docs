---
description: This page shows the key building blocks of the solution.
---

# architecture overview

The following diagram provides an at-a-glance view of the platform design. This is a work in progress, and will be updated as requirements are clearer, and roadmap steps come into scope. The current horizon for this design is the Platform MVP, which will drive the initial delivery. Each building block will be further broken down to identify responsibilities in the forms of interfaces, data and function.

![Architecture Overview Diagram](../.gitbook/assets/eccoo-architecture-overview.png)

## System Context \(a.k.a the outside the system boundary\)

The primary system roles, Care Receiver and Care Giver \(two variants: volunteer and paid\), are shown to the top of the diagram. A supporting role of Care Arranger may act on behalf of the Care Receiver. This could be a family or community member, or a care professional. The converse of this role: the facilitator offering guided performance, is an eccoo-provided role offering telephone-based \(?\) support to users.

System-to-system interactions already identified are:

* SMS Service
* Email Service
* eccoo bank

## System Narrative

At heart the platform marries a graph database which tracks relationships between people and groups \(such as circles\) with a ledger which manages the exchange of value between these people. As such, it can be thought of as a transaction-oriented social network.

The system comprises a series of interlocking subsystems, each with a defined purpose.

* The [identity and access subsystem](component-designs/identity-and-access-subsystem/) is responsible for controlling the security of the platform. The [identity](component-designs/identity-and-access-subsystem/identity-component.md) store enables people to be registered in the platform, and is used to underpin authentication and [authorisation](component-designs/identity-and-access-subsystem/authorisation.md) services. The related audit service records significant events within the system, such as who is accessing care records.
* The [relationships subsystem](component-designs/relationships-subsystem/) mediates all caring [relationships](component-designs/relationships-subsystem/relationship-component.md) within the platform, including the [matching](component-designs/relationships-subsystem/matching-component.md) of users with care needs to care givers. It also manages the [roles](component-designs/relationships-subsystem/roles-component.md) that platform users fulfil \(a.k.a. hats\), as well as storing [care notes](component-designs/relationships-subsystem/care-notes-component.md) and [appointment](component-designs/relationships-subsystem/appointments-component.md) details.
* The [transactions subsystem](component-designs/transactions-subsystem/) facilitates the exchange of value that the platform enables. The [care logging](component-designs/transactions-subsystem/care-logging.md) component tracks the appointments that a care giver has completed, and enables [payments](component-designs/transactions-subsystem/payments.md) to be made. Care receivers are able to make payments to their personal accounts.
* The [channels subsystem](component-designs/channels-subsystem/) manages interaction with the platform. A [sign-up](component-designs/channels-subsystem/sign-up-component.md) component manages the initial process of registering a user with the platform. From then on, the platform users will interact platform via their individual profile. The [notification management](component-designs/channels-subsystem/notification-management-component.md) component will manage any outbound notifications, taking into account user contact preferences. The [guided performance](component-designs/channels-subsystem/guided-performance-component.md) component allows temporary performance of platform actions on behalf of a user.

