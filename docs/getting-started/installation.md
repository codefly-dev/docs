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
