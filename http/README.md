# HTTP Repository Connector
The HTTP implementation of the [Repository Connector](https://github.com/Knotx/knotx-repository-connector#repository-connector)
that allows to fetch documents from an external repository via HTTP protocol.

## How does it work
HTTP Repository Connector uses an HTTP Client to communicating with the remote repository.
An HTTP repository destination is defined by:
- `scheme` - connection scheme: `http` or `https`
- `domain` - domain or the IP of the host: e.g. localhost, 10.0.11.2
- `port` - port on which the host listens, e.g. 8080, 3001, etc.
Repository passes (configured) certain request headers from the original client request 
to the remote repository (`allowedRequestHeaders`).


## How to use
Simply configure a connector as the [Server Routing Operation Handler](https://github.com/Knotx/knotx-server-http#routing-operations),
using `httpRepoConnectorHandler` factory, e.g. 
```hocon
routingOperations = [
  {
    operationId = my-operation
    handlers = [
      // other handlers
      {
        name = httpRepoConnectorHandler
        config = {
          // connector configuration
        }
      }
      // other handlers
    ]
  }
]

```

### Detailed configuration
All configuration options are explained in details in the [Config Options Cheetsheet](https://github.com/Knotx/knotx-repository-connector/tree/master/http/docs/asciidoc/dataobjects.adoc).
