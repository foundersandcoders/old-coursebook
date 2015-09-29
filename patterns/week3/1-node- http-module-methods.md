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

Class: http.Agent   


HTTP Agent is used for pooling sockets used in HTTP client requests, allowing you to keep them open until the client is ready to make a request.
It allows the connection to remain open when experiencing a large number of requests but still does not require the developer to close HTTP clients
>A socket is an end-point of an inter-process communication across a computer network, it waits on the server for requests from a client
The client-server data exchange takes place when a client connects to the server through a socket.



*  new Agent([options])

The options Object Set of configurable options to set on the agent for example

* keepAlive - boolean value, keeps sockets for use by future requests. Default: false 
* keepAliveMsecs - integer value, when using keepAlive it determines how often to send TCP KeepAlive packets over sockets being kept alive. Default: 1000 (keepAlive = true)
* maxSockets - number of max sockets allowed per host. Default: infinity
* maxFreeSockets - number of max sockets to leave open in a free state. Default: true (keepAlive = true)

TCP keepAlive packet is an ACK (signal that data has been received successfully) with the sequence number set to one less than the current sequence number for that connection
keepAlives are used to verify that the computer at the remote end of a connection is still available 

If there is no response to a keepAlive, it is re-sent every (keepAliveMsecs)

*  agent.maxSockets

By default set to Infinity. Determines how many concurrent sockets the agent can have open per origin. Origin is either a 'host:port' or 'host:port:localAddress' combination.


*  agent.maxFreeSockets

By default set to 256. For Agents supporting HTTP KeepAlive, this sets the maximum number of sockets that will be left open in the free state.


*  agent.sockets

An object which contains arrays of sockets currently in use by the Agent. Do not modify.


*  agent.freeSockets

An object which contains arrays of sockets currently awaiting use by the Agent when HTTP KeepAlive is used. Do not modify.


*  agent.requests

An object which contains queues of requests that have not yet been assigned to sockets. Do not modify.


*  agent.destroy()

Destroy any sockets that are currently in use by the agent.


It is usually not necessary to do this. However, if you are using an agent with KeepAlive enabled, then it is best to explicitly shut down the agent when you know that it
 will no longer be used. Otherwise, sockets may hang open for quite a long time before the server terminates them.
 

*  agent.getName(options)

Get a unique name for a set of request options, to determine whether a connection can be reused. In the http agent, this returns host:port:localAddress. In the https agent, 
the name includes the CA, cert, ciphers, and other HTTPS/TLS-specific options that determine socket reusability.










