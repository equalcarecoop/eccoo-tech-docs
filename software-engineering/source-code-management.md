---
description: This page describes the approach to managing source code across
---

# source code management

## Repository

We manage our source code using git, with central management and sharing via a GitLab.com group. This is currently being run under a free plan, which will suffice for the initial development. We chose GitLab over other services such as GitHub and Bitbucket as they offer both private repositories and a generous 2000 hour monthly allowance on CI \(Continuous Integration - automated test and build actions\) usage on the free tier.

Developers will need to have a [gitlab.com](https://gitlab.com/) account, which can be set up to link to other service sign-ins, including GitHub accounts.

Platform code is managed in the [eccoo Platform](https://gitlab.com/eccoo-platform) GitLab group.

![View of the source code management within GitLab](../.gitbook/assets/image%20%283%29.png)

We have made the top-level group \(eccoo Platform\) public. This will enable us to release code as open source when we decide. We have made the Services subgroup private. This makes it invisible to anyone who is not added to the group. We will set up additional subgroups as we need them to contain other parts of the codebase \(e.g. UI code\).

New users can request access by contacting Giles Dring via Slack \(more admins will be added as people register\).

### Branching

Given the small size of the team, we will use a trunk-based development model checking in to the master branch. We will tag significant releases or create specific locked branches. These concepts are broadly similar in git. Developers are responsible for either rebasing their changes on the central master branch  before committing, or creating short lived \(1-2 days maximum\) branches in the event that this becomes impossible.

### Commit messages

We will use git commit messages to document changes. There is a lot of great advice on writing good commit messages. We will follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) standard. These follow the structure outlined below:

```text
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

For documentation follow the link, but a couple of examples are given.

#### Full style

This documents a commit which fixes issue 133 \(referenced in the footer\). It contains a summary line which references the type \(fix\) and a short description of what's changed. This is followed, after a separating blank line, by the full description. Finally, there are some footers which capture additional information. These could be used within automation as practices evolve.

```text
fix: correct minor typos in code

see the issue for details on typos fixed.

Reviewed-by: Z
Refs #133
```

#### Short style

Many changes are trivial, and writing a full commit message would be overkill. For those, a summary line will suffice.

```text
docs: correct spelling of CHANGELOG
```

### Continuous Integration / Continuous Delivery

We will use the [Gitlab CI/CD](https://gitlab.com/help/ci/README.md) tool to run test suites and perform deployment activity on every commit. We will document the individual pipelines within each project, as they will differ depending on the code being managed.

## Open sourcing strategy

We will manage the code as closed source in the first instance, with a view to open sourcing components as we develop them. Our aspiration is towards openness, but this is balanced with a need to recognise the commercial value of our platform. We will agree this position with the cooperative members when it becomes appropriate.

