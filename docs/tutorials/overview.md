# Tutorials

Requirement:

- Docker running
> For now, pull the image by hand
```shell
docker pull codeflydev/companion:0.0.0
```

## Create a 4-tier application

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

Go to the frontend service and run

```shell
codefly add depependency
```







