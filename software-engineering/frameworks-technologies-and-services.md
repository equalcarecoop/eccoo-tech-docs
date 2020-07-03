---
description: >-
  This page outlines the key frameworks in use within the platform, with links
  to documentation and suggestions for self-paced learning.
---

# frameworks, technologies and services

## Application Code

### NestJS

The bespoke services are written in [NestJS](https://nestjs.com/). This is a JavaScript / TypeScript framework which provides a strong structure on top of the Express framework. It makes heavy use of structures such as classes and [modularisation](https://docs.nestjs.com/modules), and software engineering techniques like [dependency injection](https://docs.nestjs.com/providers). This means that the code should be easily testable and maintainable. It also means that there is a bit more of a learning curve getting up to speed.

The UI and Graph API layer are built using NestJS.

Resources:

* [Documentation](https://docs.nestjs.com/)
* [First Steps](https://docs.nestjs.com/first-steps)
* The Overview and Fundamentals sections of the documentation provide a good overview of the core of NestJS. Other sections can be dipped into as required.

### GraphQL

The API within the platform is expressed in [GraphQL](https://graphql.org/). This is a query language which provides a clean structure for querying backend resources, avoiding some of the pitfalls and inefficiencies of alternative approaches such as REST. GraphQL was developed by Facebook and open sourced in 2015. Given we are storing our data in a graph, GraphQL is a great fit.

The UI will query the Graph API using GraphQL. This means that developers in the frontend will need a good handle on the queries and mutations, whereas the API developers will require an understanding of implementation concepts like schemas, types and resolvers.

Resources

* The [Learning](https://graphql.org/learn/) section of the GraphQL documentation.
* [How To GraphQL](https://www.howtographql.com/) self-paced learning

### Sass



### Nunjucks

Resources

* [https://mozilla.github.io/nunjucks/getting-started.html](https://mozilla.github.io/nunjucks/getting-started.html)
* [https://css-tricks.com/killer-features-of-nunjucks/](https://css-tricks.com/killer-features-of-nunjucks/)

### TypeScript



### Keycloak



### Neo4j



## CI / CD

### Jest



### GitLab CI



## Infrastructrure

### Docker



### Ansible











