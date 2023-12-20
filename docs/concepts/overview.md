# Concepts

## Codefly Software Development Model

Codefly encourages and help you to organize your code. The fundamental hierarchy is:

- Organization
- Workspace
- Project
- Application
- Service

> **Note** Organizations, workspaces provide **isolation** level for large or complex businesses. For most usages, a global organization and workspace is recommened.

### Project

A project typically corresponds to a business line. They are meant to be completely independent.

A project is made of Applications.

> **Example**: A project could correspond to your monorepo in your company.

[Details](project.md)

### Application

An application is a group of services that work together to provide some functionality to your system.

> **Important** Behavior for an application is provided **only** by its services. This happens when some service endpoints are declared with an **application** visibility.

[Details](application.md)

> **Note** An application corresponds closely with the concept of "Bounded Context" in Domain-Driven Design.

### Service

A service is also a logical component but backed up by some processing power!

> **Important** The role of a service is to provide some behavior exposed through its endpoints.

Endpoints define the behavior of the service.

> **Example** A web server is a service with a HTTP endpoint.

It can be a single container or a collection of them.

Services expose endpoints with different visibilities:
- private: access allowed only to other services in the same application
- application: access allowed to other application services
- public: access allowed to external users

> **Example** Redis caching is a service with two endpoints: **read** and a **write**. Whether the underlying deployment uses a single instance or master/replicas or cluster doesn't matter. Other services should only be made aware of the two endpoints.

[Details](service.md)

### Endpoints

[Details](service.md)
