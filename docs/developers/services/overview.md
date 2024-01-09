## We summarize dependency between agent phases


### Runtime

Endpoints describe the API of the service, Network Mappings are how these endpoints are reached.

For each service, there are two types of endpoints that the service exposes:

### Intrinsic endpoints

These are the endpoints that the Service provides by itself.

In 1. the backend has an intrinsic endpoint: the REST endpoint. The Gateway doesn't have intrinsic endpoints: its endpoints come from the dependencies from from other services: `dependency endpoints`.

In theory, we could loop infinitely with the new endpoints being used, etc...
