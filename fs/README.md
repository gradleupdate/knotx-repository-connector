## Filesystem Repository Connector
The Filesystem implementation of the [Repository Connector](https://github.com/Knotx/knotx-repository-connector#repository-connector)
that allows to fetch documents from the local filesystem.

## How does it work
Filesystem Repository Connector uses [Vert.x Filesystem](https://vertx.io/docs/vertx-core/java/#_using_the_file_system_with_vert_x) 
to read files from the local filesystem in asynchronous way.

## How to use
Simply configure a connector as the [Server Routing Operation Handler](https://github.com/Knotx/knotx-server-http#routing-operations),
using `fsRepoConnectorHandler` factory, e.g.  
```hocon
routingOperations = [
  {
    operationId = my-operation
    handlers = [
      // other handlers
      {
        name = fsRepoConnectorHandler
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
All configuration options are explained in details in the [Config Options Cheetsheet](https://github.com/Knotx/knotx-repository-connector/tree/master/fs/docs/asciidoc/dataobjects.adoc).
