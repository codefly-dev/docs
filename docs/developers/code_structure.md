# Components

codefly is built from the ground up to build, test, deploy and maintain microservices based architectures.

We follow as best as we can the philosophy of Domain Driven Design (DDD).

Here are from highest level to lowest the structure of system in codefly.

## Workspace

This is the highest level in codefly where logical dependencies can be handled.

_Examples_:
- a mono-repository can be represented as a workspace or as a collection of independent workspaces.
- dependent components, a website and a backend should belong to the same workspace.


## Module

A module is codefly term for **bounded context** in DDD.

This corresponds to a group of services who can communicate by default with each other using **private** endpoints.

## Service

Will contain all the code required to run a service as well as some configurations.

# Code Structures

codefly allows different layouts to map components to code structure.

In the layout diagrams, `${something}` a variable, can be the name of an environment or a service.

### Flat Layout

This corresponds to a single module containing all service.

This _default_ module will be identified with the workspace itself and not exposed to the user.


_Examples_:
- 3-Tier applications

```
workspace/
├── 📂 configurations
|   ├── 📂 ${dev}
│   └── 📂 ${production}
└── 📂 services
│   ├── 📂 ${frontend}
│   ├── 📂 ${backend}
│   └── 📂 ${database}
```


### Module Layout

This is the preferred organization as we map logical to physical separation.


```
workspace/
├── 📂 configurations
|   ├── 📂 ${dev}
│   └── 📂 ${prod}
└── 📂 modules
│   └── 📂 ${management}
|       └── 📂services
|           ├── 📂 ${backend}
|           ├── 📂 ${cache}
|           └── 📂 ${database}
│   └── 📂 ${external}
|           ├── 📂 ${frontend}
|           └── 📂 ${api}
```
