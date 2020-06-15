---
description: This page describes the design of hosting and IT operations for the platforms
---

# infrastructure design

**TL;DR** It's Amazon Web Services, but without being locked-in.

The platform will be hosted in AWS in the first instance. Where possible, it will avoid being tied in to AWS components, unless these are based on accepted open standards. The trade-off here is the ability to move to an alternative platform offset against a greater degree of platform engineering required.

Services will be hosted as Docker containers within [Amazon ECS](https://aws.amazon.com/ecs/) \(Elastic Container Services\).

## Types of hosting

The platform will be hosted on some form of cloud service. This \(rightly\) rules out buying / renting, installing and running physical hardware and managing network provisioning. This would be a costly and risky endeavour, and procuring and installing the hardware would be likely to take a significant period of time. Cloud hosting provides the following benefits:

* It can be very rapid to turn on / turn off computing resources and you only pay for what you use.
* Implementation risks are reduced, particularly with the more commoditised cloud services, as service providers will invest in design and testing their configurations.
* Cloud operations practices such as monitoring / alerting, backups, and security management are more likely to be 

There are, however, many varieties of cloud:

* Infrastructure as a Service \(IaaS\) means renting a 'virtual server/storage/networking'. The customer \(i.e. Equal Care Co-op\) would design, build and manage/operate everything from the operating system upwards.
* Platform as a Service \(PaaS\) means deploying code and configuration onto a managed runtime environment. This generally either means a container platform such as Docker, or an abstracted function runtime such as AWS Lambda. Similarly, many cloud providers also offer Database as a Service \(DBaaS\) running  
* Software as a Service \(SaaS\) means using configured Enterprise services such as Customer Relationship Management, HR, email or other productivity tools. Salesforce and GSuite are examples of SaaS cloud services.

[This IBM article](https://www.ibm.com/uk-en/cloud/learn/iaas-paas-saas) provides a good overview of these different approaches.

A simple infrastructure stack is listed below, showing the layers provided by each of the cloud types.

| Element | IaaS | PaaS | SaaS |
| :--- | :---: | :---: | :---: |
| Hosted Application |  |  | ✓ |
| Development tools, Databases, Business Analytics |  | ✓ | ✓ |
| Operating Systems |  | ✓ | ✓ |
| Servers and Storage | ✓ | ✓ | ✓ |
| Networking firewalls/security | ✓ | ✓ | ✓ |
| Data center physical plant/building | ✓ | ✓ | ✓ |

## Hosting Recommendations

PaaS is the most appropriate approach for the eccoo platform. As implied above, there is some variety in this. The table below outlines some alternative of hosting approaches, with some headline thoughts on each.

| Hosting Variant | Flexibility | Risk | Time-to-market |
| :--- | :--- | :--- | :--- |
| Provider Agnostic Docker Containers | High. Can move to other Docker providers | Highest. All application infrastructure design responsibility of Equal Care Co-op | Longest. Design takes time, as does testing |
| AWS | Moderate. Some lock-in/investment, but many brand-leading platforms provides choice. Cost-effective deployment means procuring reserved instances. | Low. AWS economies of scale mean significant design in commodity PaaS. | Short. Many out of the box solutions  mean that infrastructure can be stood up very fast. High quality documentation. |
| Microsoft Azure | Similar to AWS in broad terms, although Microsofts approach to cost-management is to negotiate enterprise agreements, which may not suit the platform. | Similar to AWS | Short. Similar to AWS. Documentation not quite as broad. |
| Google Cloud | Google challenging AWS and Azure, although range of products smaller at the moment. | Similar to other Cloud providers | Likely to be comparable to AWS and Azure. |

A pure provider agnostic approach would require more design and ongoing operation time from the development team. Given the need for the developers to deliver the platform, this is not an ideal scenario.

It may be that a hybrid approach provides the flexibility and control required.

The ZDNet article [https://www.zdnet.com/article/google-cloud-gains-in-gartners-2019-cloud-infrastructure-magic-quadrant/](https://www.zdnet.com/article/google-cloud-gains-in-gartners-2019-cloud-infrastructure-magic-quadrant/) reports industry research company Gartner suggesting that AWS still leads the other providers. Azure was blighted by outages in its core Active Directory component during 2019, and as already mentioned, Google Cloud lacks some critical technologies. Cost is not a significant differentiator.

The following table outlines the product selections in each scenario.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Component</th>
      <th style="text-align:left">Provider Agnostic</th>
      <th style="text-align:left">AWS</th>
      <th style="text-align:left">Azure</th>
      <th style="text-align:left">Google Cloud</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Graph Database</td>
      <td style="text-align:left">Neo4j</td>
      <td style="text-align:left">Amazon Neptune</td>
      <td style="text-align:left">Azure CosmosDB with Gremlin API</td>
      <td style="text-align:left">None available</td>
    </tr>
    <tr>
      <td style="text-align:left">Ledger Database</td>
      <td style="text-align:left">Hyperledger Fabric (alternatively Hyperledger Iroha or Hyperledger Sawtooth)</td>
      <td
      style="text-align:left">
        <p>Amazon QLDB or Amazon Managed Blockchain</p>
        <p>(NB Both new. Not yet UK-hosted)</p>
        </td>
        <td style="text-align:left">Azure Blockchain Service (NB preview)</td>
        <td style="text-align:left">None available</td>
    </tr>
    <tr>
      <td style="text-align:left">Identity and Access</td>
      <td style="text-align:left">Keycloak</td>
      <td style="text-align:left">Amazon IAM</td>
      <td style="text-align:left">Azure Active Directory</td>
      <td style="text-align:left">Cloud IAM</td>
    </tr>
    <tr>
      <td style="text-align:left">API Layer</td>
      <td style="text-align:left">Javascript + framework</td>
      <td style="text-align:left">Lambda</td>
      <td style="text-align:left">Azure Functions</td>
      <td style="text-align:left">Cloud Functions</td>
    </tr>
    <tr>
      <td style="text-align:left">UI App</td>
      <td style="text-align:left">Web Server + Single Page App (SPA) using Vue.js</td>
      <td style="text-align:left">AWS Amplify + SPA</td>
      <td style="text-align:left">Web Apps + Mobile Apps (?)</td>
      <td style="text-align:left">App Engine (?)</td>
    </tr>
    <tr>
      <td style="text-align:left">Containers</td>
      <td style="text-align:left">n/a</td>
      <td style="text-align:left">Amazon ECS / Amazon EKS</td>
      <td style="text-align:left">Container Instances / AKS (Kubernetes)</td>
      <td style="text-align:left">App Engine / Google Kubernetes Service</td>
    </tr>
  </tbody>
</table>

## Operations

The infrastructure must be manageable. This means

* Monitoring and alerting will be required
* Some form of on-call capability needed, given hours of operation
* While Identity and Access Management should be self-service, there will be a need for credential and exceptional access management.
* Management infrastructure should be segregated from main platform \(separate network\)
* It must not be possible to contravene security controls as a management user

## Recommendations

Due to the desire of Equal Care Coop to build in a portable manner, a containerised / Docker model is recommended. This has the benefit of lending itself to deployment locally for development and user testing.

Amazon Web Services is the market leading cloud service provider. I recommend selecting AWS for the MVP given its maturity and the ease of locating development partners skilled in the platform.

