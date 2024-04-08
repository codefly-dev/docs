# Getting started

## Install the CLI

### MacOS

```commandline
brew tap codefly-dev/cli
```

```commandline
brew install codefly
```

### Linux

```commandline
curl -s https://raw.githubusercontent.com/codefly-dev/cli-releases/main/install/linux.sh | bash
```

### Windows

> Coming soon!

## Dependencies

`codefly` requires `Docker` to be installed on your machine and that's IT!

No local `python` installation, no manual package management, no `npm` installation, **nothing but Docker by default**!

One of the responsibilities of `codefly` [agents](../../concepts/agents.md) is to manage the dependencies for you.

## Tutorials


### Website Traffic Statistics

A very good way to get started with `codefly` is to go through the  `website traffic statistics` tutorial.

![](../assets/images/tutorials/website-visits/website.png)

This example will guide you through the process of creating a simple  3-Tier application to display traffic statistics to a website.

It will consist of a
- `web` frontend
- a `backend` API
- a `database` to store the data
- a cache to speed-up our application

There are several choices for the backend  `python`, `go`, `JavaScript` and more to come soon.

So let's get started: [Website Traffic Statistics](../tutorials/website-visits/introduction.md)
