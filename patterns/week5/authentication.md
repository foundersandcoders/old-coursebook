# AUTHENTICATION

Authentication is the process of determining whether someone or something is in fact who or what it
is declared to be. It verifies the identity of an individual requesting access to
certain information.

#### Authentication vs Authorisation

Authentication is the process where credentials are provided and compared with what's
on file. If they match then the process is completed and the user is granted authorisation
for access.

Authorisation is the process of an administrator granting rights and also the process of
checking user account permissions for access to resources.

### Why do we need authentication?

We need authentication as a security measure for protecting confidential data. Without
a means of verification, data access may be granted to unauthorised individuals
looking to steal confidential information and use it for their financial advantage.

Unauthorised access to data can also lead to file corruption or the downloading of
viruses which can cause a system or network to crash.

To configure authentication you have to create the following components:

* Authentication Schemes
>Includes the method used to challenge the user for credentials
An authentication scheme can include one or more steps, each of which must include
at least one plug-in.

* Authentication Plug-Ins
>An authentication plug-in is an executable shared library which participates in
the user authentication process. Plug-ins are the engines of an authentication scheme.
They implement challenge methods, map user credentials to user profile entries in
a directory, process user credentials, perform custom tasks related to the authentication
process.

* Authentication Rules
>For each policy domain, you provide one default authentication rule. Authorization
rules specify information that identifies who can access a resource it protects.



### What are the main authentication schemes?


HTTP Access Authentication Framework
If you're going the HTTP header route, you have to use a header value to authenticate
a REST client. The server is using this header value to perform authentication. It is
composed of three tokens usually:
1. An HTTP authentication name followed by
2. white space (almost always a space character), followed by
3. The scheme-specific text value.

For example: Authorization: Basic IUGWnjkfohdeuhPUHUFKJ123

* Basic Access Authentication
* Digest Access Authentication


Basic Authentication Scheme

Assumes that your credentials (the client) consists of a username and password (Base64-encoded string).
When you try to gain access to a protected realm, the server responds with a 401 which will consist of
the token "Basic" and a name-value pair specifying the name of the protected realm. For example:

```WWW-Authenticate: Basic realm="Control Panel"```



Upon receipt of the server's response, your web browser prompts you for the username and
password associated with that realm. The Authentication header for your browser's follow-up request
again contains the token "Basic" and the base64-encoded concatenation of the username, a colon,
and the password, for example:

```String concatenated = username + ":" + raw_password;```
```String schemeSpecificTextValue = base_64_encode(concatenated.toCharArray());```



Then the response will look something like:

```Authorization: Basic IUGWnjkfohdeuhPUHUFKJ123```



The server base64-decodes the credentials and compares them against the username-password database.
If it finds a match then you're in.
One of the big drawbacks of Basic is that the username and password is transmitted in plain sight.
You should not use Basic Authentication by itself, but rather with a TLS connection.

(TLS - Transport Layer Security (TLS) and its predecessor, Secure Sockets Layer (SSL),
both of which are frequently referred to as 'SSL', are cryptographic protocols designed
to provide communications security over a computer network.)



### How do HTTP cookies work?

##### What are they?
An internet cookie is a piece of text that a Web server can store on a user's hard disk.
Cookies allow a Web site to store information on a user's machine and later retrieve it.
The pieces of information are stored as name-value pairs.

##### What are their uses?
* Session Management - for example remembering what a user has in a shopping cart
* Personalization - remembers information about the user to show relevant content, Google maps (remembers home)
* Tracking - Tracks a user's browsing habits - page visit frequency, sequence and duration

##### Implementation
Cookies are arbitrary pieces of data which are sent backwards and forwards with every
request the user makes on a domain.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/HTTP_cookie_exchange.svg/1400px-HTTP_cookie_exchange.svg.png)

Cookies are created by the domain using an HTTP ```Set-Cookie``` sent in an HTTP response. This
header instructs the browser to store the cookie and send it back with future requests from the
server.

Here's a written example of how cookie requests/responses work-

1) ```GET /index.html HTTP/1.1```
```Host: www.example.org```

The server responds with two ```Set-Cookie``` headers -

2) ```HTTP/1.0 200 OK```
```Content-type: text/html```
```Set-Cookie: theme=light```--> theme is a session cookie, deleted by the browser when it closes
```Set-Cookie: sessionToken=abc123; Expires=Wed, 09 Jun 2021 10:18:14 GMT``` --> expires attribute instructs the browser
to delete the cookie at a specific date and time


Next, the browser sends another request to visit the ```spec.html``` page on the website.
This request contains the ```Cookie``` header which contains the two cookies that the
server instructed the browser to set.

3) ```GET /spec.html HTTP/1.1```
```Host: www.example.org```
```Cookie: theme=light; sessionToken=abc123```

A ```Cookie``` can be modified by the server using the ```Set-Cookie``` header in the
response. The browser then replaces the old value with the new value.


Setting Cookies with Javascript

Javascript can create, read and delete cookies with the document.cookie property.
 For example a cookie can be created like this:

 ```javascript
 document.cookie="username=Jack Carlisle";
 ```
You can also add an expiry date:

```javascript
document.cookie="username=Jack Carlisle; expires=Thu, 18 Dec 2050 12:00:00 UTC";
```
With a path parameter you can tell a browser which path the cookie belongs to. By
default, the cookie belongs to the current page

```javascript
document.cookie="username=Jack Carlisle; expires=Thu, 18 Dec 2050 12:00:00 UTC; path=/";
```


### What are JSON web tokens and how do you use them?

JSON Web Tokens are an alternative to cookies, the main difference being that they
allow the servers to remain stateless (not having to remember information about
the client). When sending a cookie, the server recognises that cookie and then looks
up information about that client. With JWTs the HTTP responses and the requests
contain all of the information within the token itself. This is useful when web apps
are run across multiple servers.

When the client makes a POST request containing login credentials the server
then creates the JWT with a secret key that allows the server to verify the client
the next time that client makes an HTTP request.

There are three parts to a JWT:

1. The Header
>Contains the meta-data for the token and at a minimal contains the type of the
signature and/or encryption algorithm

2. Claims (Payload)
>Contain any information that is associated with the user. It can contain arbitrary
information that we specify.

3. JSON Web Signature
>The headers and claims are digitally signed using the algorithm specified in the
header.

![](https://files.gitter.im/foundersandcoders/authentication/0qMG/Screen-Shot-2015-10-12-at-15.08.20.png)



What is bcrypt and how do you use it?

What method of authentication would you recommend?
