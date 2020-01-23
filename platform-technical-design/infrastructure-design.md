# infrastructure design

## Constraints

Cloud hosting - prefer not AWS, due to ethical concerns

Should therefore aim for cloud-agnostic, which implies not relying on cloud-native technologies \(e.g. Identity and Access Management components such as AWS IAM\).

Core platform should not be SaaS, as this is differentiator. Could consider SaaS for non-core \(e.g. contact centre services\).

## Operations

The infrastructure must be manageable. This means

* Monitoring and alerting will be required
* Some form of on-call capability needed, given hours of operation
* While Identity and Access Management should be self-service, there will be a need for credential and exceptional access management.
* Management infrastructure should be segregated from main platform \(separate network\)
* It must not be possible to contravene security controls as a management user

