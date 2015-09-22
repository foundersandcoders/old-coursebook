# What's in a HTTP request?

Whenever your web browser fetches a file (a page, a picture, etc) from a web server, it does so using HTTP - that's "Hypertext Transfer Protocol".  HTTP is a request/response protocol, which means your computer sends a request for some file (e.g. "Get me the file 'home.html'"), and the web server sends back a response ("Here's the file", followed by the file itself).

That request which your computer sends to the web server contains all sorts of (potentially) interesting information.  <!-- regular html comment We'll now examine the HTTP request your computer just sent to this web server, see what it contains, and find out what it tells me about you.-->

![](http://shvetsgroup.com/files/images/HTTP_request.png)
