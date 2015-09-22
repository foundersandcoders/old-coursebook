### What is an HTTP status code and what are the most common ones?

#### 1xx Informational

Status codes starting with '1' signal that the request has been received and that the process is continuing.

#### 2xx Success

Status codes starting with '2' indicate that the action requested by the client was received, understood, accepted and processed successfully.

##### 200 OK

Standard response for successful HTTP requests. The actual response will depend on the request method used. In a GET request, the response will contain an entity corresponding to the requested resource. In a POST request, the response will contain an entity describing or containing the result of the action.

#### 3xx Redirection

Status codes starting with '3' indicate that further action is required by the client. Sometimes this action is required by the user, but sometimes the user agent completes this action on behalf of the user. A typical example of when this class of codes is used is in URL redirection; the required action is to redirect to a site at a different URL; and the browser completes this request (ie no user interaction is needed).

##### 301 Moved Permanently

This is a redireciton code. It tells the client that this request and all future requests should be redirected to the given URI.

#### 4xx Client Error

##### 403 Forbidden

##### 404 Not Found

#### 5xx Server Error


### References

[Glossary of HTTP response codes from Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes)

[List of HTTP status codes on Wikipedia](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
