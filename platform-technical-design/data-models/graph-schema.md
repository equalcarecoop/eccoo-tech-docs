---
description: This page outlines the domain model that will underpin the Social Graph
---

# graph schema

{% hint style="info" %}
It might help you to review these web pages before reading this page. I've listed them in approximately increasing order of complexity.

* [https://graphql.org/learn/](https://graphql.org/learn/)
* [https://graphql.org/learn/thinking-in-graphs/](https://graphql.org/learn/thinking-in-graphs/)
* [https://neo4j.com/blog/why-graph-databases-are-the-future/](https://neo4j.com/blog/why-graph-databases-are-the-future/)
* [https://neo4j.com/developer/guide-data-modeling/](https://neo4j.com/developer/guide-data-modeling/)
* [https://neo4j.com/blog/data-modeling-basics/](https://neo4j.com/blog/data-modeling-basics/)
{% endhint %}

We use a graph database to represent the relationships managed within the system.

It is important that we get this terminology correct as it will form the common language between the users and developers of the platform.

{% hint style="success" %}
Please provide feedback and edits on the terms I am using. None of these are yet tested or implemented!
{% endhint %}

The diagram below shows an overview of the schema which should cover MVP. This is subject to detailed UX and technical design work.

![Graph Schema Overview](../../.gitbook/assets/graph-schema-overview-relationships.png)

Please note, the items in a red colour \(namely Value Exchange and Expense\) are not yet implemented.

## Descriptions

### Person

The core of the model is a representation of a person who is then expressed in a series of different ways by the Hats that they wear. These _Hats_ can be seen in the model as they link directly to the 'abstract' Person interface with a dotted line and an open arrowhead.

### User

The user is the first 'hat' for every person registered in the system. This enables the creation of the core of the profile, and will be assigned when any user registers.

### Giving

This hat is applied to people who provide care in the system, regardless of whether this is paid or unpaid care and support. This may be resolved by a separate label which segregates these two whilst enabling one person to do both \(for example, giving care for a family member and also offering paid care and support to others\).

People: Giving: Paid or People: Giving: Unpaid.

### Receiving

This hat is worn by people who receive care and support within the system. 

### Arranging

This hat represents people who are responsible for arranging care on behalf of a person receiving. They can be said to represent that person and to work in their interests. This role is extremely variable, ranging from an oversight and information access through to active management of the bookings, introductions and reviews. It is best represented by the [Team Co-ordinator](https://app.gitbook.com/@eccoo/s/policies/safe-and-well/roles-and-responsibilities/the-team/team-co-ordinator) role description. 

Note the person arranging may also be giving care and support to the person receiving and the person receiving may also be arranging their own care and support and giving or arranging support for others.

### Booking

A booking is ATTENDED\_BY two or more Users. They OCCUR\_AT a location. They may result in Expenses to be paid to a Platform User and may enable value exchange from a Person Giving to a Person Receiving and vice versa.

### Location

A location represents a physical or a virtual address \(WhatsApp group, phone call, zoom link etc\) and will be modelled with the appropriate attributes.

### Value Exchange

This may not actually form part of the graph - but it is a recognition that the main thing to flow from an appointment is that some value is exchanged in terms of support or care given and transactions made. This will need to be captured somehow.

### Expense

This is the representation of an out of pocket expense to be paid back to a user. In most cases, this will be a Person Giving.



## Other concepts to explore

The following concepts are likely to be needed, but are as yet ill defined.

* Contact Details
* Notes, shared with the person receiving's Team
* Profile information for both person giving and person receiving
* Review of how the booking went
* Messages to other people in the person's Team





