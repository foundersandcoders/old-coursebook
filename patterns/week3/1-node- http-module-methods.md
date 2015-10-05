# Http Core module and it's methods

The objects that you return by the http protcol or the request have methods in node. The response and the request can be manipulated by these methods which are part of node http core module. An example of a http node method would be `request.write()`.

Node.js has several modules compiled into the binary (for example "http" or "fs". These modules are described in greater detail elsewhere in node documentation.
Core modules are always preferentially loaded if their identifier is passed to `require()`. For instance, `require('http')` will always return the built in HTTP module, even if there is a file by that 



The HTTP interfaces in Node.js are designed to support many features of the protocol which have been traditionally difficult to use. In particular, large, possibly chunk-encoded, messages.

For perfromance its best to only `require()` the modules you are using.



###Class: http.ServerResponse
This object is created internally by a HTTP server--not by the user. It is passed as the second parameter to the 'request' event. for example when we made our handler functions.

####response.writeHead(statusCode[, statusMessage][, headers])

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

####response.statusCode

When using implicit headers (not calling response.writeHead() explicitly), this property controls the status code that will be sent to the client when the headers get flushed.

Example: `response.statusCode = 404;`
After response header was sent to the client, this property indicates the status code which was sent out.



####response.setHeader(name, value)

Sets a single header value for implicit headers. If this header already exists in the to-be-sent headers, its value will be replaced. Use an array of strings here if you need to send multiple headers with the same name.

Example:
```javascript
response.setHeader("Content-Type", "text/html");
or

response.setHeader("Set-Cookie", ["type=ninja", “language=javascript”]);
```

####response.write(chunk[, encoding][, callback])

If this method is called and response.writeHead() has not been called, it will switch to implicit header mode and flush the implicit headers.

This sends a chunk of the response body. This method may be called multiple times to provide successive parts of the body.

chunk can be a string or a buffer. If chunk is a string, the second parameter specifies how to encode it into a byte stream. By default the encoding is 'utf8'. The last parameter callback will be called when this chunk of data is flushed.

Note: This is the raw HTTP body and has nothing to do with higher-level multi-part body encodings that may be used.

The first time response.write() is called, it will send the buffered header information and the first body to the client. The second time response.write() is called, Node.js assumes you're going to be streaming data, and sends that separately. That is, the response is buffered up to the first chunk of body.

Returns true if the entire data was flushed successfully to the kernel buffer. Returns false if all or part of the data was queued in user memory. 'drain' will be emitted when the buffer is free again.

####response.end([data][, encoding][, callback])

This method signals to the server that all of the response headers and body have been sent; that server should consider this message complete. The method, response.end(), MUST be called on each response.

If data is specified, it is equivalent to calling response.write(data, encoding) followed by response.end(callback).

If callback is specified, it will be called when the response stream is finished.

####response.finished

Boolean value that indicates whether the response has completed. Starts as false. After response.end() executes, the value will be true.

###Class: http.Agent   

>A socket is an end-point of an inter-process communication across a computer network, it waits on the server for requests from a client
The client-server data exchange takes place when a client connects to the server through a socket.
HTTP Agent is used for pooling sockets used in HTTP client requests, allowing you to keep them open until the client is ready to make a request.
It allows the connection to remain open when experiencing a large number of requests but still does not require the developer to close HTTP clients

An example of when you would want to use http.Agent is when you are making requests for multiple bits of data, like photos on instagram related to a specific user or hashtag. http.Agent keeps the connection open so as the server can continue to respond to the request i.e. continue to send you instagram photos from a specific source.


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










