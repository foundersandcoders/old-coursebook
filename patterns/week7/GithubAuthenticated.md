# GitHub Authentication

### Part 1: How to get the Auth Token

1. Set up your server.
2. Register a new application on Github (do this in your developer applications). [Link.]( https://github.com/settings/applications/)
3. Make sure your URL includes 'https://'
4. In your frontend redirect user to github login which will create a code in the url that you will need to use.

  ```javascript
    window.open('https://github.com/login/oauth/authorize?client_id=YOUR_CLIENT_ID')
  ```

5. Once they have logged in they will be redirected to your callback URL.
6. Make sure there is an endpoint to deal with this callback URL in your handler.
7. Authentication needs to be done over https so you will need to require that.
8. Inside this you will need to create a function (which takes the code and a callback as arguments).

  ```javascript
  function authenticate(code, callback) {
  }
  ```

9. This function sends a POST request to gitHub with your client ID, client secret (which are saved as environment variables) and the code from your url. You will need to require querystring and qs.stringify your data object to allow the authentication key to pop forth.

  ```javascript
  var data = {
      client_id: process.env.clientId,
      client_secret: process.env.clientSecret,
      code: code
  };
  var stringData = qs.stringify(data);
  var reqOptions = {
      host: 'github.com',
      path: '/login/oauth/access_token',
      method: 'POST',
  };
  ```

9. You will need to deal with the access token data coming back as chunks. When it is complete, run a callback with the body as the sole argument.
10. This callback function will store your access token.

You can see how we started with this on our [repo.](https://github.com/rug1/githubAuth)


### Part 2: Storing Access Token

To be continued...

You can look how FCScripters did this [here.](https://github.com/fcscripters/Devs-In-The-Detail/blob/master/index.js#L131)


### References
http://fajitanachos.com/Authenticating-with-the-GitHub-API/

https://github.com/prose/gatekeeper
