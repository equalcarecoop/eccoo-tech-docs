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

* The [sign-up](component-designs/sign-up.md) component manages the initial process of creating a user identity \(managed by [Authentication](component-designs/security/authentication.md)\) and a profile \(managed by [Individual Profile](component-designs/individual-profile.md)\). This identity has a role assigned in the [Role Manager](component-designs/role-manager.md).
* If signing up as a care received, matching can then take place to attempt to forge a link with a care giver. This is mediated by the [matching](component-designs/matching.md) component which attempts to match based on the criteria held in the relative profiles \(assumed to be needs, skills and other criteria such as location and availability\).
* Once a match has been established, the relationship is stored in the [Relationship Graph](component-designs/relationship-graph.md). This will, in conjunction with the role manager and [authorisation](component-designs/security/authorisation.md) component, enable fine-grained permissions over personal information managed in the system.
* The [Appointment Booking](component-designs/appointment-booking.md) component is responsible for enabling users to arrange meetings. Initially this will be between care givers and care receivers, but ultimately the concepts could be reused to cover circle or interest group meetings.
* Some of these meetings will be to deliver care to care receivers: to facilitate payment, these will be tracked in the [Care Logging](component-designs/care-logging.md) component. Care notes associated with these meetings will be logged in the [Care Notes](component-designs/care-notes.md) component. This will be associated with the care receiver, and accessible to the care giver.
* \[Payment handling interactions are to be determined, but will be managed via the [payments](component-designs/payments.md) component\]
* All components are likely to need to notify the users, which they will do via the [notification management](component-designs/notification-management.md) component. User contact preferences will also be managed here.
* The need for guided performance is recognised by the [guided performance](component-designs/guided-performance.md) component. This will allow the temporary performance of system actions on behalf of a user.

