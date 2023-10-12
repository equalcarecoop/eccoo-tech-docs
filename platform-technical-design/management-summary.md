---
description: >-
  This provides an overview of the contents of the document, including suggested
  next steps.
---

# management summary

This document translates the requirements captured in the backlog which define ‘what our users need’ into a high-level architecture design which specifies ‘what we are going to build’.

The architecture is based on three core elements:

* **Graph**\
  the primary role of the platform is to build and maintain a strong set of relationships around care. The use of a graph-oriented database focussed on this social network strongly aligns the architecture with the purpose of Equal Care Coop. Using the open source, industry leading Neo4j Graph Database provides a robust data store. Exposing this via a GraphQL API layer provides strong domain design, robust API specification, development flexibility and runtime efficiency. Over time, the Graph will extend from the MVP focus of people, roles, appointments and care notes to include circle tools, sociocratic decision making and ad-hoc support network formation.
* **Ledger**\
  the other key aspect of the system is to exchange value between its participants in a trusted and traceable manner. In the MVP this covers tracking caring interaction from completed appointment to payment. Over time, this will extend to encompass management of complex funding arrangements from multiple sources, distribution of transactions to care providers, the care coins e-currency and a raft of other concerns such as cooperative governance. This is an excellent candidate for a private permissioned blockchain, fronting the contract with a GraphQL or RESTful API.
* **Identity**\
  underpinning both the Graph and Ledger is a trusted reference to the platform users identity. This includes registration, authentication and authorisation. The Identity subsystem will use industry standards OpenID / OAuth to distribute the identity to the other elements

These are accessed by various channels, web-based in the case of the MVP, but ultimately expanding to include other channels such as voice. The web-oriented channels will use the Vue.js framework to provide a flexible, modular Single Page application.

{% hint style="info" %}
For now, the UI Layer is not currently Vue.js (or in fact anything heavily client-side). We're building in a Nest.JS / Express server-side app with pages templated with Nunjucks.

This is largely down to concerns over ensuring we have robust approaches to accessibility.

We may look at augmenting the frontend with something like Svelte - potentially replacing modules with standalone FE apps as appropriate.
{% endhint %}

The tech stack is shown below:

![Recommended tech stack for eccoo Platform MVP](<../.gitbook/assets/eccoo stack.png>)

Grey boxes are subject to final validation. In particular, the transaction log selection of blockchain technology is being considered in the context of the Gartner Hype Curve: Equal Care Coop will not just be another blockchain bandwagon jumper.

## Next Steps

* UX designer to define the roles for the MVP
* Dev Lead to work with Technical Director to specify technology stack to deliver architecture

