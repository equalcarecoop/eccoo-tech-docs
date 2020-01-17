# relationships

The relationships component is one half of the platform core, with [care logging](care-logging.md). This component enables the multiple relationships enabled and required by the platform to be tracked:

* person-person: I provide care to you
* person-role: I am a care giver and a circle administrator - a.k.a. hats
* person-circle: I am part of the Blackshaw Head circle

The relationship component will implement a [social graph](https://en.wikipedia.org/wiki/Social_graph), similar to the graph underpinning social media platforms such as Facebook.

{% hint style="info" %}
It is important to distinguish between the concept of a social graph and the implementation of such well-known commercial Social Networks. The former merely stores the relationships between entities \(e.g. people\), whereas the latter attempts to use this knowledge for shareholder gain. It is, in other words, a question of intent.
{% endhint %}

## ​C​ritical requirements

## ​Implementation

[Graph databases](https://en.wikipedia.org/wiki/Graph_database) are an efficient and scalable means of managing this kind of data. The most popular such technology is [Neo4j](https://neo4j.com/). This has an open source Community Edition, as well as a series of [paid subscriptions](https://neo4j.com/subscriptions), including a Startup tier which offers free access to the enterprise-grade features.

