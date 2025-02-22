[![Go Reference](https://pkg.go.dev/badge/github.com/yxxhero/tail.svg)](https://pkg.go.dev/github.com/yxxhero/tail#section-documentation)
![ci](https://github.com/yxxhero/tail/workflows/ci/badge.svg)
[![FreeBSD](https://api.cirrus-ci.com/github/yxxhero/tail.svg)](https://cirrus-ci.com/github/yxxhero/tail)
# tail functionality in Go

yxxhero/tail provides a Go library that emulates the features of the BSD `tail`
program. The library comes with full support for truncation/move detection as
it is designed to work with log rotation tools. The library works on all
operating systems supported by Go, including POSIX systems like Linux, *BSD,
MacOS, and MS Windows. Go 1.12 is the oldest compiler release supported.

A simple example:

```Go
// Create a tail
t, err := tail.TailFile(
	"/var/log/nginx.log", tail.Config{Follow: true, ReOpen: true})
if err != nil {
    panic(err)
}

// Print the text of each received line
for line := range t.Lines {
    fmt.Println(line.Text)
}
```

See [API documentation](https://pkg.go.dev/github.com/yxxhero/tail#section-documentation).

## Installing

    go get github.com/yxxhero/tail/...

## History

This project is an active, drop-in replacement for the
[abandoned](https://en.wikipedia.org/wiki/HPE_Helion) Go tail library at
[hpcloud](https://github.com/hpcloud/tail). Next to

## Examples
Examples, e.g. used to debug an issue, are kept in the [examples directory](/examples).
