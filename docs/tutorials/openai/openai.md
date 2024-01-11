# Memento: From zero to OpenAI application: a Tutorial for the ages

Rather than using some "hello world" project, we will create from scratch most of complete system, all the way to CI/CD of a complex application with several components!

`codefly` value is **making development** easier and faster but don't trust us and decide for yourself!

> We want to build Momento, a web application that lets you upload your content and let you ask questions about it!

As you can imagine, it is not a trivial application to build! But with `codefly`, we will build it steps by steps.

Following this journey with us, you will get to appreciate the power of `codefly` as the most powerful Developer Platform.

> Note: Some steps are optional, and require an AWS account for a proper production development but the large majority can be done locally!


Part I: User management

Obviously, you don't want let everyone uploading documents to your `memento` and even more importantly, you don't want to let anyone getting access to information about other users data!

As 99.9% of software systems, we need to manage users, authentication and authorization: part I is about this.

Tech stack:
- Auth0 for our Identity provider
- `go` server for User Management
- AWS RDS for storage

Let's get started by creating a project `memento`:

```shell
codefly add project memento
```

Now, let's create an application that will contain all services required for proper user management:

```shell
codefly add application user_management
```

> Note: `codefly` keeps track of what you are working on (project, application, service) so most commands with `codefly` can be ran for anywhere.
> Running `codefly` inside a particular application or service directory will overwrite the "active" context.

```shell
codefly context
```

Navigate to your project (or application or service) code:

```shell
codefly open project
```

> Note: it will open VS Code, but you can specify your favorite editor like this `--editor=goland`.

In particular, you will see that there is `providers/local` folder: this will contain credentials used for local environment.

Copy there your Auth0 configuration `auth0.env` there:
```env
AUTH0_ISSUER_BASE_URL=xxx
AUTH0_CLIENT_ID=xxx
AUTH0_CLIENT_SECRET=xxx
...
```

Now, let's start the actual work:

[1. Creating a `go` server](1_user_management.md)
