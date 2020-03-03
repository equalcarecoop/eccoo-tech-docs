# relationships subsystem

The relationships subsystem is one half of the platform core, partnering the [transactions subsystem](../transactions-subsystem/). This component enables the multiple relationships enabled and required by the platform to be tracked:

* person-person \([relationships](relationship-component.md)\): I provide care to you
* person-role \([roles](roles-component.md)\): I am a care giver and a circle administrator - a.k.a. hats
* person-circle: I am part of the Blackshaw Head circle

The relationships subsystem is clustered around a Graph database which efficiently manages the social network enabled by the platform. This technology also lends itself to tracking [appointments](appointments-component.md) and [care notes](care-notes-component.md). The [matching](matching-component.md) algorithms will use the graph as a primary source when building carer recommendations.

The circles and other team-related aspects of the subsystem are out of scope for the MVP.

NB there is currently some fluidity in the location of the roles component - it will either be part of the relationships subsystem, or may better reside in the identify and access subsystem. This is to be resolved once the technology stack has been selected.

## Candidate technologies

The core of the subsystem will be a [graph database](https://en.wikipedia.org/wiki/Graph_database) servicing the other components. These are an efficient and scalable means of managing this kind of data. The most popular such database is [Neo4j](https://neo4j.com/). This has an open source Community Edition, as well as a series of [paid subscriptions](https://neo4j.com/subscriptions), including a Startup tier which offers free access to the enterprise-grade features. Cloud platforms also offer graph database services, including Amazon Neptune and Azure Cosmos DB's Gremlin API.

Each of the other components in this subsystem will be written as an API application exposing a defined interface to wrapper and control access to the graph. Implementation technology is less critical, and will be driven by the hosting and graph database product selected.



