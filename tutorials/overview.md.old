# Random thoughts about *why codefly*


## devtime vs runtime
Runtime is a term that everybody agrees on. There is not really any corresponding terms for the domain in which codefly is used.
So we can propose "devtime" as for "development time". Usually this is divided into Day 1/ Day 2.

Runtime has plenty of APIs: you build functionality by coordinating behavior from different components through APIs.
Devtime doesn't have any "API": there is no "update your go modules" API, or "verify your SBOM for security threats" API.
Goal of codefly is to introduce APIs for devtime.

APIs are grouped into Agent types. See Concepts/Agent for more details.

## Monolith/Micro-services

Microservices, aka, modern application development requires foundation and tooling on another level compared to monolith.

Successful tech companies developed this tooling in-house to suits their need.

Most companies can't afford (money or time) to get proper foundation for microservices tooling.

There are three common paths:
- they don't try, build a monolith, accumulate technical debt until it becomes unmanageable and need a huge effort to break the monolith
- they try and slowly develop a distributed monolith until the system crumbles under its own weight and back to square one.
- they try and manage to keep the tech debt down and the velocity up while adding up "niceties" to their distributed system.

codefly aims to make modern easy powerful application development available to everyone, with DevX that we aim to make the best in the world. Period.

## DevOps gone wrong

Note that microservices is often associated DevOps.

Like everything bad, DevOps started with some good intention but ended up a terrible implementation (like Scrum).
It now means developers should learn about Docker, kubernetes (the implementation details) even to get started.
This is crazy: progress in productivity comes usually from a "narrowing" of set of skills (with a deepening of those -- think typical "Fordism"). But here, we ask Developers to *widen" their skills.
A "subtle" goal of codefly is to go back to the original intention of DevOps: important to know not only what the code does but how as well while keeping implementation details out. That *shouldn't* include writing kubernetes manifests.

### Joe Beda on k8s:
The point Joe Beda makes is that while Kubernetes is a powerful tool for container orchestration, its complexity is such that it's more practical and efficient for most developers to interact with it through higher-level abstractions and tools, rather than directly managing the lower-level details and configurations. This approach leads to better productivity and allows developers to focus more on building their applications rather than the intricacies of Kubernetes itself.
TODO: Find quote

## Agile on top of things

Combine Microservice + DevOps with Agile and you end up with a time bomb: developers have incentives pushing things out as soon as possible and therefore, no work is done to build the foundation of a good microservice development system.
The distributed monolith is usually the consequence of it.

## Templates are way too weak an "abstraction"

In IDP (Internal Developer Platform) and other systems that aim to make development easier and faster, systems usually rely on templates.
We believe this is way too weak a system (and by definition it is not really an abstraction at all).

Examples on writing complex helm charts are example of how difficult it can be to do anything remotely complex with templates.
The approach that codefly follows is to use agent, which are mini application in themselves with precise API to do everything for a service from creation (the implementation for agent uses templating).

> Templates are an implementation detail of the Create API of a Service Agent.


# Tutorials

Instead of having different "hello world" useless tutorials, I thought we could do Tutorials in a bunch of "Series". Each series will be a github repository and needs to be able to be ran.

Since the goal of codefly is to go from zero to a production setup, it makes sense that each Series start from zero and end up in "Production".


> What is production here? Deployment is very standard up to local k8s.
> After, it really depends on what deployment strategy you pick (CD tooling, etc...)
> So I can maybe end each iteration with local k8s deployment.
> Should we do [Optional] steps in CD?


Each series will have several "iterations".

So a first series can be:

## Series 1: User Management

Goal is to have a frontend + API that let user register/login/etc...and have some profile information.

It will require
- a frontend with an identity provider -- right now, we have Auth0 + Nextjs
- API gateway to do authentication AND authorization
- backend in go
- RDS database

## Iteration 1: Frontend + Server

### Objectives

Show the "spirit" of codefly in the shortest amount of time.

Showing some of the main commands of the CLI
- add
- context
- run

### Steps

- [CLI create] application
- [CLIL create] services frontend and server
- [CLI create] dependency server <- frontend
- [CLI run] the stack
- show frontend
- show [codefly control tower]
- show the version in the frontend using [codefly SDK]
- update the version in server to show [codefly generic hot-reloading]

## Iteration 2: Adding and viewing a User

### Objectives

Very short iteration to because it also introduces gRPC.

### Steps

- User Create/Get in proto
- show [hot-reloading] in server
- Auth0 setup + wiring with backend

## Iteration 3: Adding data

TODO


----------------------------------------------


Requirement:

- Docker running
> For now, pull the image by hand
```shell
docker pull codeflydev/companion:0.0.0
```

## Create a 4-tier application

### Goal


Why 4 and not the usual 3-tier application?

> A common pattern in micro-services architecture is to add an API gateway between your users and your backend services.

### Create a project

```shell
codefly add project spa
```

Let's navigate to our project:

```shell
codefly open project --editor=goland
```

Replace `goland` by your favorite editor.

### `Web` application for your frontend and your API gateway

```shell
codefly add application web
```

#### Add the frontend

```shell
codefly add service frontend --agent=nextjs-auth0:0.0.31
```

> Note: latest is the preferred way, but it's broken right now

From anywhere, you can run the frontend

```shell
codefly run service
```

#### TODO: krakend

### Backend application for server and data

```shell
codefly add application backend
```

We choose `go+gRPC` for the backend.

```shell
codefly add service server  --agent=go-grpc:0.0.63
```

Run the server
```shell
codefly run service
```

### Add a dependency

Go to the frontend service, or change the context of `codefly` back and run
```shell
codefly context switch application
```

```shell
codefly add dependency
```

Run again, now it will automatically run the server as well!

> Hot-reloading only works in stand-alone mode, will be fixed SOOON.

### CLI Frontend

You can get a good view of your projects by going to http://localhost:10001







