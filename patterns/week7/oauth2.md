# OAuth2

There is a walkthrough :walking: lower down this page :point_down: for you to follow.

## What is OAuth2?

OAuth 2 is an authorization framework that enables applications to obtain *limited access* to user accounts on an HTTP service such as **Facebook**, **GitHub**, and **DigitalOcean**. It’s often referred to as a ‘valet for the web’ because it grants an application access to protected data only for *specific* uses and often a limited amount of time :clock6:

An app might request permission to access your facebook profile. However, once you comply, the app **cannot** use that data for anything more than allowing you to play the game and post you in-game achievements to facebook (and  who doesn’t want to tell their friends how sick they are at candy crush? :candy::candy:)

Once the *authentication* and *validation* process begins, the user is driven to a secure URL where credentials are requested, but those credentials are **never** shared outside of that secure URL.

### The benefits of OAuth2

* **Ease**: Using OAuth is like being able to save your password **securely** into your browser. :lock: You won’t have to type in your password every time an app wants to access data on your behalf
* **Time** :clock5: Who wants to re-create a new identity for every website? (Not us!) Using popular social media sites like twitter and facebook as your log-in to other apps takes the pain out of using other services :ok_hand:
* **Networking**: Using one user profile (e.g. facebook) to comment on *many* websites means other users can look you up on your preferred page
* **Privacy**: With Oauth third parties need never have access to any of your financial information as you’ll be redirected to your banking app to complete the transaction :credit_card:
* **Security**: Since OAuth2 all data transfers must take place over [SSL](https://www.instantssl.com/ssl.html).  SSL ensures the most stringent industry cryptography procedures are being used at all times
* **Control**: Users can decide when web tokens can expire

### The drawbacks of OAuth2

* **Reliance**: If you use one account to log into many sites, then a hack on that site or account will have implications across many places :confounded:
* **Phishing** :fishing_pole_and_fish: If users are not diligent then becoming used to logging in with a few centralised usernames and passwords could leave them open to malicious sites
* **Lack of Anonymity**: If OAuth is implemented to use one of your public social media profiles then it may be a choice that certain users are not comfortable with.

### How does OAuth2 work?

There are **four** parties involved in the OAuth2 framework:

* Resource Owner - the user   
* Auth Server - external server (e.g. Github)  
* Client Application - your frontend  
* Resource Server - your server  

The steps for authentication are as follows:

1) The **resource owner** asks the client application to *do something* e.g. (“hello client application! I want to tweet about how great FAC is! :heart:”)  

2) The **client application** says to the **resource server** "The resource owner wants to tweet about that awesome academy in Bethnal Green"  

3) The **resource server** tells the **client application** - "I would love to promote free education, but I can’t help you - you need a token first!"  

4) The **client application** says to the **auth server** "Can I have a token please?" n.b. a few substeps here  

5) The **auth server** asks the **resource owner** for a username (D Sofer) and password (1L0v3L1b3rtyX)  

6) The **resource owner** responds to the **auth server** with the password and *very* wisely picked password  

7) The **auth server** sends back a token to the **client application**  

8) The **client application** sends token to **resource server**  

9) The **resource server** asks the **auth server** who the user is, verifies the tokens, and then allows Dan to tweet about how great he thought LX Riddle was :question:  

### Authentication Flow Diagram with tokens

![oauth2](https://files.gitter.im/hdrdavies/dtpx/rsz_oauth2.png)

### Walkthrough for creating a simple Github login using OAuth2

As promised, here is our walkthrough: https://github.com/Conorc1000/Oauth2Tutorial

#### Resources

OAuth2 Authorisation Framework: http://tools.ietf.org/html/rfc6749  
Toolkit for NodeJS: https://github.com/t1msh/node-oauth20-provider  
OAuth via Github: https://developer.github.com/v3/oauth/  
OAuth Authorisations API documentation: https://developer.github.com/v3/oauth_authorizations/  
