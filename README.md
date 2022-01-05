# YoMo CLI

Command-line tools for YoMo

## Binary

`curl -sL https://github.com/yomorun/cli/releases/download/v0.1.5/yomo-v0.1.5-`uname -m`-`uname -s`.tar.gz | tar xvfz -`

OR

`curl -fsSL "https://bina.egoist.sh/yomorun/cli?file=yomo" | sh`

## Build from source

[Installing Go](https://golang.org/doc/install)

You can easily install the latest release globally by running:

```sh
go install github.com/yomorun/cli/yomo@latest
```

Or you can install into another directory:

```sh
env GOBIN=/bin go install github.com/yomorun/cli/yomo@latest
```

## Getting Started

### 1. Source

#### Write a source app

See [example/source/main.go](https://github.com/yomorun/cli/blob/main/example/source/main.go)

#### Run

```sh
go run main.go
```

### 2. Stream Function

#### Init

Create a stream function

```sh
yomo init [Name]
```

#### Run

```sh
yomo run --name [Name] app.go
```

### 3. Stream Function to store data in DB

#### Write a stream function

See [example/stream-fn-db/app.go](https://github.com/yomorun/cli/blob/main/example/stream-fn-db/app.go)

#### Run

```sh
yomo run --name [Name] app.go
```

### 4. YoMo-Zipper

#### Configure YoMo-Zipper `workflow.yaml`

```yaml
name: Service
host: localhost
port: 9000
functions:
  - name: Noise
  - name: MockDB
```

#### Run

```sh
yomo serve --config workflow.yaml
```

## Example

### Prerequisites
[Installing task](https://taskfile.dev/#/installation)

### Simple Example

#### Run

```sh
task example
```

### Edge-Mesh

#### Run US Node

```sh
task example-mesh-us
```

#### Run EU Node

```sh
task example-mesh-eu
```
