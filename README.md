# go-opml

 [![Build Status](https://travis-ci.org/gilliek/go-opml.png?branch=master)](https://travis-ci.org/gilliek/go-opml)

go-opml aims to be a Go package for parsing OPML files.

This library is forked from https://github.com/gilliek/go-opml to add the following new features

## Features
- Ability to generate a new OPML file from scratch
- Ability to add a RSS Feed from URL into an existing OPML struct

## Installation

```go get github.com/oxtyped/go-opml/opml```

## Usage

Parse OPML from file:

```go
package main

import (
	"fmt"
	"log"

	"github.com/oxtyped/go-opml/opml"
)

func main() {
	doc, err := opml.NewOPMLFromFile("path/to/file.xml")
	if err != nil {
		log.Fatal(err)
	}

    xml, _ := doc.XML()
	fmt.Println(xml)

    //...
}
```


Parse OPML from URL:

```go
package main

import (
	"fmt"
	"log"

	"github.com/oxtyped/go-opml/opml"
)

func main() {
	doc, err := opml.NewOPMLFromURL("http://www.example.com/file.xml")
	if err != nil {
		log.Fatal(err)
	}

    xml, _ := doc.XML()
	fmt.Println(xml)

    //...
}
```

Generate a new OPML file from scratch and add RSS feeds manually:

```go
package main

import (
	"fmt"
	"log"

	"github.com/oxtyped/go-opml/opml"
)

func main(){

  doc := opml.NewOPMLFromBlank("title of OPML file")

  doc.AddRSSFeedFromURL("http://www.example.com/rss.xml")

  xml, _ := doc.XML()
  fmt.Println(xml)

  //...
}
```
## Documentation

Document can be found on [GoWalker](https://gowalker.org/github.com/gilliek/go-opml/opml) 
or [GoDoc](http://godoc.org/github.com/gilliek/go-opml/opml)

## License

BSD 3-clauses
