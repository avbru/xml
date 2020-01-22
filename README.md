This package is basically golang encoding/xml fork with fixes to support:
* omitempty tag for struct fields
* omitempty tag for nested xml tags 
 
```
type Test struct {
	Nested  struct {
	Something string
	}  `xml:"nested,omitempty"`
	NestedWithPath string `xml:"nested1>nested2>nestedwithpath,omitempty"`
}
``` 

Example:

https://play.golang.org/p/wGPvdvlObFA
