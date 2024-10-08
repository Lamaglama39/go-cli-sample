# go-cli-sample

A CLI tool that simply displays "Hello World!"+α in Go.

## Installation

Please download and run the binary file corresponding to each platform from [Releases](https://github.com/Lamaglama39/go-cli-sample/releases).

## Usage

When you run the `go-cli-sample` command, "Hello World!" is displayed.

```shell
$ go-cli-sample
Hello World!
```

You can change the "Hello" part with the `--word` or `-w` flag.

```shell
$ go-cli-sample -w Hi
Hi World!
$ go-cli-sample --word Hi
Hi World!
```

The subcommand `hi` is implemented.  
When executed, "(・´ｪ`・) Hi!" is displayed instead of "Hello World!".

```shell
$ go-cli-sample hi
(・´ｪ`・) Hi!
```

Version information can be found using the `--version` or `-v` flag.

```shell
$ go-cli-sample --version
$ go-cli-sample hi --version
```

You can display the description with the `-h` flag.

```shell
$ go-cli-sample -h
$ go-cli-sample hi -h
```

## Development

### Requirement

- Docker version 27.3.0

### Using packages

- [cobra-cli](https://github.com/spf13/cobra-cli)
- [GoReleaser](https://goreleaser.com/)

```shell
RUN go install github.com/spf13/cobra-cli@v1.8.1
RUN go install github.com/goreleaser/goreleaser@latest
```

### util command

* update dependencies
```
go mod tidy
```
* format
```
gofmt .
```
* static check
```
go vet .
```

## local build

* check .goreleaser.yaml
```
goreleaser check
```

* local build
```
goreleaser release --snapshot --clean
```

## release

```
git tag vX.X.X
```
```
git push origin vX.X.X
```

## Author

Lamaglama39

- [X](https://x.com/lamaglama39)

## License

[MIT License](https://github.com/Lamaglama39/go-cli-sample/blob/main/LICENSE)
