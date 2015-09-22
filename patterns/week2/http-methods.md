# What are HTTP methods and what does each one do?

Def: 'http request method' = methods used for a request-response between a client and server.

A client can use one of these request methods, to send an HTTP request message to a server.

### GET and HEAD methods are in charge of retrieving information. These methods are considered 'safe' because they should have no other effect on the data it is retrieving.

1) GET: retrieves information from the given server using a given URI.

2) HEAD: only retrieves the status line and header sections of the data that GET would otherwise retrieve. This might be used instead of GET to check against the local cache copy.

### POST, PUT and DELETE methods may be considered 'unsafe'.

3) POST: sends data to the server (using HTML forms).

4) PUT: requests the server to store the data sent using POST. The data sent overwrites the data sent previously.

5) DELETE: requests the server to delete the data stored by PUT.

6) TRACE: requests the server to report back the actions that it takes.

7) CONNECT: requests the server to establish a connection to a destination specified. If the client tries to retrieve information from an HTML page, the server will send this request, and retrieve the response for the client on his behalf.

```
Client <--------------------> Remote destination

Client ------> (Server) -----> Remote destination
     ^----------      ^----------  
```
8) OPTIONS: requests the server to return a list of request methods that it supports.


#Notes:
- These method names are case sensitive - make sure they are all UPPERCASE.
- Information required for a request to be understood by the server seems to differ slightly, depending on HTTP/1.0 or HTTP/1.1. For more information, please refer to: http://www.tutorialspoint.com/http/http_methods.htm
- Resources used. Please refer to the websites below for more information:
  - http://www.w3schools.com/tags/ref_httpmethods.asp
  - http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html
  - http://www.tutorialspoint.com/http/http_methods.htm
