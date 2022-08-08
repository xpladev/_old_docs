---
weight: 10
title: Install xplad
---

# Install `xplad`

`xplad` is the command-line interface and daemon that connects to Xpla and enables you to interact with the Xpla blockchain. Xpla core is the official Golang reference implementation of the Xpla node software.

This guide is for developers who want to install `xplad` and interact with Xpla core without running a full node. If you want to run a full node or join a network, visit [Run a Full Xpla Node]({{< ref "run-a-full-xpla-node" >}}).

### Prerequisites

- [Golang v1.18 linux/amd64](https://golang.org/doc/install)
- Ensure your `GOPATH` and `GOBIN` environment variables are set up correctly.
- Linux users: install [build-essential](http://linux-command.org/en/build-essential.html).

{{< hint warning >}}
**xplad for Mac**  
If you are using a Mac, follow the [`xplad` Mac installation guide]({{< ref "xplad-mac" >}}).
{{< /hint >}}

## From Binary

The easiest way to install `xplad` and Xpla core is by downloading a pre-built binary for your operating system. You can find the latest binaries on the [releases](https://github.com/c2xdev/core/releases) page. If you have a Mac, follow the [Mac installation instructions]({{< ref "xplad-mac" >}}).

## From Source

### 1. Get the Xpla core source code

Use `git` to retrieve [Xpla core](https://github.com/c2xdev/core/), and check out the `main` branch, which contains the latest stable release.

```
git clone https://github.com/c2xdev/core
cd core
git checkout [latest version]
```

### 2. Build Xpla core from source

Build Xpla core, and install the `xplad` executable to your `GOPATH` environment variable.

```bash
make install
```

### 3. Verify your Xpla core installation

Verify that Xpla core is installed correctly.

```bash
xplad version --long
```

The following example shows version information when Xpla core is installed correctly:

```bash
name: xpla
server_name: xplad
version: v2.0.0
commit: ea682c41e7e71ba0b182c9e7f989855fb9595885
build_tags: netgo,ledger
go: go version go1.18.2 darwin/amd64
```

{{< hint info >}}
**Tip**  
If the `xplad: command not found` error message is returned, confirm that the Go binary path is correctly configured by running the following command:
```sh
export PATH=$PATH:$(go env GOPATH)/bin
```
{{< /hint >}}

## Next steps

For more information on `xplad` commands and usage, see [Using xplad]({{< ref "using-xplad" >}}).
