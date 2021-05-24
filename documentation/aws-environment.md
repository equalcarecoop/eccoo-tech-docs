---
description: Describes how to set up a new AWS environment
---

# AWS environment

## Prerequisites

### Set up new certificates for the environment

In the AWS console set up the required certificates or the environment in the ACM \([https://eu-west-2.console.aws.amazon.com/acm](https://eu-west-2.console.aws.amazon.com/acm)\).

You will need to set up certs to cover:

* The main domain: for non-live environments, this will be `<env>.equalcare.coop`
* The related subdomains: `graph`, `identity`, `chat`.
* Any other domains required \(e.g. `beta`\)
* The subdomains could be covered by a wildcard.

Once that is complete, make a note of the ARN for the certificate.

## Ansible config

### Files

The two files that are required are:

* `platform/<env>.yaml`
* `secret/<env>.yaml`

You will also need to update the accounts.yaml and platform-cloud.yaml file to list the new environment. This should be done on the branch with the same name as the environment.

### Initialisation order

Stand up the services in the following order by commenting out services not to be stood up in platform/&lt;env&gt;.yaml, as follows:

#### Identity

```text
stacks:
  - identity-access
  # - neo4j
  # - graph-api
  # - ui
  # - chat
```

Once stood up, login to the new service.

Select the **Realm Settings** menu item, then the **Security Defenses** tab.

Set the _Content Security Policy_ to include the chat url for the environment in frame-ancestors.

Select **Clients** then _Web_ from the list.

On the **Settings** tab, set the root URL and valid redirect URLs for the web client.

![](../.gitbook/assets/image%20%285%29.png)

On the **Credentials** tab, regenerate the client secret. Record this in the infrastructure config platform/&lt;env&gt;.yaml file.

### Graph, UI, and Rocket Chat

```text
stacks:
  - identity-access
  - neo4j
  - graph-api
  - ui
  - chat
```



