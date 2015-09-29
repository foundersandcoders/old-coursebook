# Http Core module and it's methods

The objects that you return by the http protcol or the request have methods in node. The response and the request can be manipulated by these methods which are part of node http core module. An example of a http node method would be `request.write()`.

Node.js has several modules compiled into the binary (for example "http" or "fs". These modules are described in greater detail elsewhere in node documentation.
Core modules are always preferentially loaded if their identifier is passed to `require()`. For instance, `require('http')` will always return the built in HTTP module, even if there is a file by that 



The HTTP interfaces in Node.js are designed to support many features of the protocol which have been traditionally difficult to use. In particular, large, possibly chunk-encoded, messages.

For perfromance its best to only `require()` the modules you are using.

Class: http.ServerResponse
This object is created internally by a HTTP server--not by the user. It is passed as the second parameter to the 'request' event. for example when we made our handler functions.

response.writeHead(statusCode[, statusMessage][, headers])

Sends a response header to the request. The status code is a 3-digit HTTP status code, like 404. The last argument, headers, are the response headers. Optionally one can give a human-readable statusMessage as the second argument.

Example:
```javascript
var body = 'hello world';
response.writeHead(200, {
  'Content-Length': body.length,
  'Content-Type': 'text/plain' });
```
This method must only be called once on a message and it must be called before response.end() is called.

If you call response.write() or response.end() before calling this, the implicit/mutable headers will be calculated and call this function for you.

Note that Content-Length is given in bytes not characters. The above example works because the string 'hello world' contains only single byte characters. If the body contains higher coded characters then Buffer.byteLength() should be used to determine the number of bytes in a given encoding. And Node.js does not check whether Content-Length and the length of the body which has been transmitted are equal or not.










