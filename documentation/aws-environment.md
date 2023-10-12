---
description: Describes how to set up a new AWS environment
---

# AWS environment

## Prerequisites

### Set up new certificates for the environment

In the AWS console set up the required certificates or the environment in the ACM ([https://eu-west-2.console.aws.amazon.com/acm](https://eu-west-2.console.aws.amazon.com/acm)).

You will need to set up certs to cover:

* The main domain: for non-live environments, this will be `<env>.equalcare.coop`
* The related subdomains: `graph`, `identity`, `chat`.
* Any other domains required (e.g. `beta`)
* The subdomains could be covered by a wildcard.

Once that is complete, make a note of the ARN for the certificate.

## Ansible config

### Files

The two files that are required are:

* `platform/<env>.yaml`
* `secret/<env>.yaml`

You will also need to update the accounts.yaml and platform-cloud.yaml file to list the new environment. This should be done on the branch with the same name as the environment.

### Initialisation order

Stand up the services in the following order by commenting out services not to be stood up in platform/\<env>.yaml, as follows:

#### Identity

```
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

![](<../.gitbook/assets/image (17).png>)

On the **Credentials** tab, regenerate the client secret. Record this in the infrastructure config platform/\<env>.yaml file.

### Rocket Chat

```
stacks:
  - identity-access
#  - neo4j
#  - graph-api
#  - ui
  - chat
```

This will attempt to start up the rocket chat service, which will fail, as additional database setup is required. This can be done by running a task from definition mongo-setup-db-\<env>. This should be in the environment cluster, and within the cluster VPC. The networks should be the same as the chat-db service. Allocate it to the chat-frontend security group. It should run, then stop.

The cloudwatch log should look like this

```
------------------------------------------------------------------------------------------------------------------------------------------------
|   timestamp   |                                                           message                                                            |
|---------------|------------------------------------------------------------------------------------------------------------------------------|
| 1621859847203 | MongoDB shell version v4.4.4                                                                                                 |
| 1621859847316 | connecting to: mongodb://chat-db.live.private.equalcare.coop:27017/rocketchat?compressors=disabled&gssapiServiceName=mongodb |
| 1621859847322 | Implicit session: session { "id" : UUID("447747a5-0e6a-4eef-a61a-220873cd842b") }                                            |
| 1621859847324 | MongoDB server version: 4.4.4                                                                                                |
| 1621859847332 | {                                                                                                                            |
| 1621859847332 |  "_id" : "rs01",                                                                                                             |
| 1621859847332 |  "members" : [                                                                                                               |
| 1621859847332 |   {                                                                                                                          |
| 1621859847332 |    "_id" : 0,                                                                                                                |
| 1621859847332 |    "host" : "chat-db.live.private.equalcare.coop:27017"                                                                      |
| 1621859847332 |   }                                                                                                                          |
| 1621859847332 |  ]                                                                                                                           |
| 1621859847332 | }                                                                                                                            |
| 1621859847897 | {                                                                                                                            |
| 1621859847897 |  "ok" : 1,                                                                                                                   |
| 1621859847897 |  "$clusterTime" : {                                                                                                          |
| 1621859847897 |   "clusterTime" : Timestamp(1621859847, 1),                                                                                  |
| 1621859847897 |   "signature" : {                                                                                                            |
| 1621859847897 |    "hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),                                                                       |
| 1621859847897 |    "keyId" : NumberLong(0)                                                                                                   |
| 1621859847897 |   }                                                                                                                          |
| 1621859847897 |  },                                                                                                                          |
| 1621859847897 |  "operationTime" : Timestamp(1621859847, 1)                                                                                  |
| 1621859847897 | }                                                                                                                            |
| 1621859847899 | bye                                                                                                                          |
------------------------------------------------------------------------------------------------------------------------------------------------
```

You should now find that the rocket-chat-\<env> task runs stably.

Rocket Chat has started when the following shows in the cloudwatch logs for the task.

```
----------------------------------------------------------------------------
|   timestamp   |                         message                          |
|---------------|----------------------------------------------------------|
| 1621860005325 | ➔ System ➔ startup                                       |
| 1621860005326 | ➔ +----------------------------------------------------+ |
| 1621860005326 | ➔ |                   SERVER RUNNING                   | |
| 1621860005326 | ➔ +----------------------------------------------------+ |
| 1621860005326 | ➔ |                                                    | |
| 1621860005327 | ➔ |  Rocket.Chat Version: 3.14.0                       | |
| 1621860005327 | ➔ |       NodeJS Version: 12.22.1 - x64                | |
| 1621860005327 | ➔ |      MongoDB Version: 4.4.4                        | |
| 1621860005327 | ➔ |       MongoDB Engine: wiredTiger                   | |
| 1621860005328 | ➔ |             Platform: linux                        | |
| 1621860005328 | ➔ |         Process Port: 3010                         | |
| 1621860005328 | ➔ |             Site URL: https://chat.equalcare.coop  | |
| 1621860005328 | ➔ |     ReplicaSet OpLog: Enabled                      | |
| 1621860005329 | ➔ |          Commit Hash: 1255c8f0ca                   | |
| 1621860005329 | ➔ |        Commit Branch: HEAD                         | |
| 1621860005329 | ➔ |                                                    | |
| 1621860005329 | ➔ +----------------------------------------------------+ |
----------------------------------------------------------------------------
```

Login to the base chat url for the environment, and follow the set-up steps.

Once that is complete, follow the setup as per [the Rocket Chat instructions](rocket-chat/).
