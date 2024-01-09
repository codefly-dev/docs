## Our `go` Server

We want a backend server (we will call it `backend` to be original) to deal with Users. We will use the very powerful `go-grpc` agent as our base.

```shell
codefly add service backend --agent=go-grpc
```

Each agent will require some configurations, though following the recommendations is usually the safe route.

To see the code created for you, you can run
```shell
codefly open service
```
Note: it will open VS Code, but you can specify your favorite editor like this `--editor=goland`.

If everything went well, you should be able to run your newly created service:

```shell
codefly run service
```

While this runs, modify the code of your service and *Magic* you get auto-reload of your code!

As you will see soon, `codefly` is *very* careful about making your Developer Experience as awesome as possible and that means doing a lot of the mundane work for you like restarting services when needed!
