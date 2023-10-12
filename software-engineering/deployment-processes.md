---
description: This page describes the deployment of the codebase to various cloud services
---

# deployment processes



![](<../.gitbook/assets/eccoo-stack-Build and Deploy.png>)

## Services

The three defined services (identity-access, graph and ui-v1) are built into a docker image which is then stored in the Gitlab Docker Registry. This can then be deployed to the cloud environment (or locally via Docker Compose). These images depend on common packages which are build separately and stored in the Gitlab Package Repo.

The docker image build and push is automated using Gitlab-CI.

## Common components

Common components, currently comprising the frontend kit and standard logger, are build into packages that can be composed into the services. The package type depends on the codebase - for the moment, we are using npm packages.

## Infrastructure Configuration Management

The configuration of the various cloud environments is managed as a set of Ansible playbooks and roles. These define the infrastructure and services required to run the various environments.

At present, this is not automatically deployed as changes are made. Further design is required around the system management services.
