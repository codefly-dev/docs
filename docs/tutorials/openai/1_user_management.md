## `go` Server

We want a backend server (we will call it `backend` to be original) to deal with Users. We will use the very powerful `go-grpc` agent as our base.

```shell
codefly add service backend --agent=go-grpc
```

Each agent will require some configurations, though following the recommendations is usually the safe route.

To see the code created for you, you can run
```shell
codefly open service
```


If everything went well, you should be able to run your newly created service:

```shell
codefly run service
```

While this runs, modify the code of your service and *Magic* you get auto-reload of your code!

As you will see soon, `codefly` is *very* careful about making your Developer Experience as awesome as possible and that means doing a lot of the mundane work for you like restarting services when needed!


## Nextjs + Auth0

To make maintenance easier, let's create a new application for the public components: the website and the API.

```shell
codefly add application frontend
```

and add the Nextjs service:

```shell
codefly add service web --agent=nexjs-auth0
```

### Add the "auth0", provider

TODO: Manual for now

Run the service
```shell
codefly run service
```

Test out the login/logout.

Now, we want the web to be aware of the backend -- we will clean it later by adding an API Gateway.

```codefly add dependency```

And pick the "backend".

Now, when running `frontnend`, it will start the backend first.

Go, to your frontend, you will see a drop down: the Frontend is now aware of the API it can call!
