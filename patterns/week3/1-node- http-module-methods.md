# Http Core module and it's methods

The objects that you return by the http protcol or the request have methods in node. The response and the request can be manipulated by these methods which are part of node http core module. An example of a http node method would be `request.write()`.

Node.js has several modules compiled into the binary (for example "http" or "fs". These modules are described in greater detail elsewhere in node documentation.
Core modules are always preferentially loaded if their identifier is passed to `require()`. For instance, `require('http')` will always return the built in HTTP module, even if there is a file by that 



The HTTP interfaces in Node.js are designed to support many features of the protocol which have been traditionally difficult to use. In particular, large, possibly chunk-encoded, messages.

For perfromance its best to only `require()` the modules you are using.








