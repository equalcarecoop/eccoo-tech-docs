# relationships

The relationships component is tasked with managing the links between people using the platform. The relationships modelled for the MVP will be relatively limited, including Carer and Assistant \(i.e. someone who arranges care for another\). This will develop over time to model a rich network of interconnections between users of the platform. This will be used to underpin the trust model: I am able to see your most sensitive care notes if I am one of your carers, but not if I am an assistant or family member.

The relationship component will implement a [social graph](https://en.wikipedia.org/wiki/Social_graph), similar to the graph underpinning social media platforms such as Facebook.

{% hint style="info" %}
It is important to distinguish between the concept of a social graph and the implementation of such well-known commercial Social Networks. The former merely stores the relationships between entities \(e.g. people\), whereas the latter attempts to use this knowledge for shareholder gain. It is, in other words, a question of intent.
{% endhint %}

## ​C​ritical requirements

* Must model carer and assistant relationships
* Must be able to create relationships
* Must be able to query for related people
* Should be able to remove relationships at the instigation of either party
* Must be able to permit or deny access to the API call based on permission claims passed by the caller.

## ​Implementation

This will be implemented as an API layer wrapping a series of graph database queries. The technology choice is not critical at this stage, and will be driven by the selection of the graph platform, the hosting decision and the skills of the development team.

