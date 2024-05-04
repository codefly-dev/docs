# Definitions and conventions

Software Development Life-Cycle follows a succession of steps.

For clarity, we group some definitions and conventions of usage by these steps.

# Generic

## Endpoint

An endpoint is a generalization of an API.

_Examples_:
- a REST backend has a REST endpoint defined by its openapi documentation
- a gRPC backend has an gRPC endpoint defined by its schema
- a redis instance has TCP endpoint

All endpoints have a a visibility. Visibility are classified as follows:
- private: accessible by default only to resources in the same module
- module: potentially accessible to resources in other module
- public: accessible from the internet


## Service

A Service is an abstraction for some compute responsible to make available a set of endpoints at any point in time.

The boundaries of what a service are completely arbitrary.

## Development

## Test

## Build

## Deploy
