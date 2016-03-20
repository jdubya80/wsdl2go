# wsdl2go

wsdl2go is a command line tool to generate [Go](https://golang.org) code
from [WSDL](https://en.wikipedia.org/wiki/Web_Services_Description_Language).

### Status

Not fully compliant with SOAP or WSDL. Works for my needs and has been
tested with a few SOAP enterprise systems.

There are limitations related to XML namespaces in Go, which might impact
how this program works. Details: https://github.com/golang/go/issues/14407.

WSDL types supported:

- [x] int
- [x] long (int64)
- [x] float (float64)
- [x] boolean (bool)
- [x] string
- [x] date
- [x] time
- [x] dateTime
- [x] complexType (struct)

Date types are currently defined as strings, need to implement XML
Marshaler and Unmarshaler interfaces.

The Go code generator (package wsdlgo) is capable of importing remote
parts of the WSDL via HTTP. You can configure its http.Client to support
authentication and self-signed certificates.