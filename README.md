Gopherjs Chrome Bindings
------------------------------------

[![GoDoc](http://godoc.org/github.com/fabioberger/chrome?status.svg)](https://godoc.org/github.com/fabioberger/chrome)

Write Chrome extensions in Golang! This library contains the necessary bindings to interact with the Chrome Javascript API in an easy and intuitive way.

**Warning:** This library is not yet complete. If there are any bindings missing that you would like to contribute, feel free to submit a pull request!

# Installation

Install with go get:

```bash
go get github.com/fabioberger/chrome
```

Then include the package in your imports:

```bash
import "github.com/fabioberger/chrome"
```

# Example Usage

This simple example will open up a new tab when the extension icon is clicked:

```go
package main

import (
	"fmt"
	"github.com/fabioberger/chrome"
	"github.com/gopherjs/gopherjs/js"
)

func main() {
	c := chrome.NewChrome()
	newTab := chrome.Object{
		"active": false,
	}
	c.Tabs.Create(newTab, func(tab chrome.Tab) {
		fmt.Println("New tab created!", tab)
	})
}
```