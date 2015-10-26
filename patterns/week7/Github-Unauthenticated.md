# Github API (Unauthenticated)

You can access the Github API as either an authenticated our unauthenticated users. Unauthenticated users can make 60 API requests per hour, whereas are authenticated users can make 5000 API requests an hour.

Unauthenticated requests can also enjoy higher rate limits given they include client ID and secret in the query string. This method should only be used for server-to-server calls. You should never share your client secret with anyone or include it in client-side browser code! 
```
$ curl -i https://api.github.com/users/whatever?client_id=xxxxxxxxxxxxxx&client_secret=yyyyyyyyyyyyyyyyyyyyy

HTTP/1.1 200 OK
Status: 200 OK
X-RateLimit-Limit: 12500
X-RateLimit-Remaining: 11966
```
[for more info visit] (https://developer.github.com/v3/#increasing-the-unauthenticated-rate-limit-for-oauth-applications)

##Checking your current rate limit status
You can check the returned HTTP headers of any API request to see your current rate limit status:
```
$ curl -i https://api.github.com/users/whatever

HTTP/1.1 200 OK
Date: Mon, 01 Jul 2013 17:27:06 GMT
Status: 200 OK
X-RateLimit-Limit: 60
X-RateLimit-Remaining: 56
X-RateLimit-Reset: 1372700873
```
 ![](https://files.gitter.im/foundersandcoders/GH-UnAuth/b9Bx/Screen-Shot-2015-10-26-at-11.32.05.png)

[Read the github documentation for checking request limit status] (https://developer.github.com/v3/#rate-limiting)
