# What's in a HTTP request?

Whenever your web browser fetches a file (a page, a picture, etc) from a web server, it does so using HTTP - that's "Hypertext Transfer Protocol".  HTTP is a request/response protocol, which means your computer sends a request for some file (e.g. "Get me the file 'home.html'"), and the web server sends back a response ("Here's the file", followed by the file itself).

Whenever you issue a URL from your browser to get a web resource using HTTP, e.g. http://www.test101.com/index.html, the browser turns the URL into a request message and sends it to the HTTP server. The HTTP server interprets the request message, and returns you an appropriate response message, which is either the resource you requested or an error message. This process is illustrated below:

![HTTP Request and Response ](https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP_Steps.png)

An HTTP message is structured as follows:
It contains a 'message header' and an optional 'message body'. The two are separated by a blank line.
The 'message header' consists of a 'request line' and 'request headers'.
![](https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/images/HTTP_RequestMessage.png)

### URLs
At the heart of web communications is the request message, which are sent via Uniform Resource Locators (URLs). URLs have a simple structure that consists of the following components:

![](https://cdn.tutsplus.com/net/authors/jeremymcpeak/http1-url-structure.png)

The protocol is typically http, but it can also be https for secure communications. The default port is 80, but one can be set explicitly, as illustrated in the above image. The resource path is the local path to the resource on the server.
```
protocol://hostname:port/path-and-file-name
```
There are 4 parts in a URL:
1. Protocol: The application-level protocol used by the client and server, e.g., HTTP, FTP, and telnet.

2. Hostname: The DNS domain name (e.g., www.test101.com) or IP address (e.g., 192.128.1.2) of the server.

3. Port: The TCP port number that the server is listening for incoming requests from the clients.

4. Path-and-file-name: The name and location of the requested resource, under the server document base directory.

For example, in the URL http://www.test101.com/docs/index.html, the communication protocol is HTTP; the hostname is www.test101.com. The port number was not specified in the URL, and takes on the default number, which is TCP port 80 for HTTP. The path and file name for the resource to be located is "/docs/index.html".

### Further Reading:

[HTTP (HyperText Transfer Protocol)
Basics](https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html)
[HTTP: The Protocol Every Web Developer Must Know - Part 1](http://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
[HTTP: The Protocol Every Web Developer Must Know - Part ](http://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-2--net-31155)
