---
description: This page outlines the development environment that will be used
---

# development environment

{% hint style="info" %}
Please update this documentation and any README documents in source code if you find any inaccurate or unclear information or instructions.
{% endhint %}

## Online services

### GitBook

We use [GitBook](https://gitbook.com) for all kinds of documentation. The platform space \(i.e. the space which this page is part of\) contains the most immediately useful information for developers.

Developers will need to a GitBook login. This can be linked to a Google or GitHub account, or can be email-based.

### GitLab

We use Gitlab for [source code management \(SCM\)](source-code-management.md). Developers will need a sign-up, and then to be added to the relevant groups.

## Developer device

{% hint style="warning" %}
These instructions are currently focussed on a macOS developer platform. There is no reason that other operating systems cannot be used.
{% endhint %}

{% hint style="info" %}
The management of local software for macOS devices is greatly enhanced by using [homebrew](https://brew.sh/). The appropriate brew command is listed after the recommended software.
{% endhint %}

Developers will need the following software:

* IDE \(Integrated Development Environment\). Our recommendation is [Microsoft Visual Studio Code](https://code.visualstudio.com/). \(`brew cask install visual-studio-code`\).
* Docker containerised runtime. \(`brew cask install docker`\)
* NodeJS runtime \(`brew install node`\)

### Visual Studio Code Configuration

{% hint style="info" %}
This section will list a set of recommended configuration for VS Code
{% endhint %}

To install plugins, either search in the Extensions browser, or use the command line

```text
code --install-extension <extension id>
```

We will use the Live Share features to facilitate remote pair working.

* Live Share `ms-vsliveshare.vsliveshare`
* Live Share Audio `ms-vsliveshare.vsliveshare-audio`

### Local Development Environment

The whole runtime can be run on a sufficiently well specified machine. This needs a lot of RAM.

To do this:

1. Clone the [Local Dev Env](https://gitlab.com/eccoo-platform/local-dev-env) project from GitLab
2. Follow the instructions in the README to set up your own version of the Equal Care Coop platform











