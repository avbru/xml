This package is basically golang encoding/xml fork with fixes to support:
* omitempty tag for struct fields
* omitempty tag for nested xml tags 
 
```
package main

import (
	"encoding/xml"	
	 oxml "github.com/avbru/xml"
)

type Test struct {
	Nested struct {
		Something string
	} `xml:"nested,omitempty"`
	NestedWithPath string `xml:"nestedL1>nestedL2>nestedwithpath,omitempty"`
}

func main() {
	d, err := xml.Marshal(&Test{})
	if err != nil {
		panic(err)
	}
	println("standart xml: ", string(d))
	
	
	d, err = oxml.Marshal(&Test{})
	if err != nil {
		panic(err)
	}
	println("oxml: ", string(d))
	
	
}

``` 

Example:

https://play.golang.org/p/wGPvdvlObFA
