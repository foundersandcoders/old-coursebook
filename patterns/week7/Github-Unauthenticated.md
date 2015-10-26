# Github API (Unauthenticated)

You can access the Github API as either an authenticated or unauthenticated user. Unauthenticated users can make 60 API requests per hour, whereas authenticated users can make 5000 API requests an hour.

Rate limits are used to control the rate of traffic sent or recieved, this can be used to prevent spamming and hacking which can cause your site to crash.

Unauthenticated requests can also enjoy higher rate limits given they include client ID and secret in the query string. This method should only be used for server-to-server calls. You should never share your client secret with anyone or include it in client-side browser code! 

```
$ curl -i https://api.github.com/users/whatever?client_id=xxxxxxxxxxxxxx&client_secret=yyyyyyyyyyyyyyyyyyyyy

HTTP/1.1 200 OK
Status: 200 OK
X-RateLimit-Limit: 12500
X-RateLimit-Remaining: 11966
```
[for more info visit] (https://developer.github.com/v3/#increasing-the-unauthenticated-rate-limit-for-oauth-applications)

However, if the rate limits are still not sufficient then authentication would be the next option. 

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

##Search API

The Search API is optimized to help you find the specific item you’re looking for (e.g., a specific user, a specific file in a repository, etc.). 
 For requests using Basic Authentication, OAuth, or client ID and secret, you can make up to 30 requests per minute. For unauthenticated requests, the rate limit allows you to make up to 10 requests per minute. 
 This is different becuase it has a different function as with a 'search api ' you wouldn't know your specific end point, it works in a similar way to google.
 
##Using cURL

cURL stands for command line url and allows a user to query an api from their command line.
e.g. 
This is an unauthenticated GET request for gihub ``` curl https://api.github.com/users/[usrename] ```





Try this tutorial : 
[tutorial] (https://gist.github.com/caspyin/2288960)

