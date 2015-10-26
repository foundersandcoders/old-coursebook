# Week 7: Project Management

## Introduction
This week we are going to look at project management. Project management is of vital importance - without good project management skills projects overrun, if they even finish at all. The two main tools that will be required in this week's project is the [Github API](https://developer.github.com/v3/) and [OAuth2](http://oauth.net/2/) authorisation. You should familiarise yourselves with these as soon as possible. As a "2.5" research goal, you should also read through the documentation for [git internals](https://git-scm.com/book/en/v1/Git-Internals). Improving your "git-fu" is always a good idea, and in the context of this week, you can do some pretty powerful stuff with a working knowledge of the github api and git internals.  
 
##Research Topics/Learning Outcomes

The research topics for this week are:
 - OAuth2
 - Github API (Unauthenticated)
 - Github API (Authenticated)
 - Git Internals   

The github API research group is split in two because github allows a significant amount to be done without requiring authentication, understanding the difference between the two methods of using the Github API is important.

###OAuth2

* [ ] Why should you use OAuth2? What are the drawbacks?
* [ ] How do OAuth2 access tokens work?

Take [OAuth2](http://oauth.net/2/) as your starting point. Your primary aim is to understand the OAuth2 standard and the security implications of utilising this standard. One particular aspect of OAuth2 to keep in mind is the need to precvent the leaking of public and private access tokens, either through hard-coding them in repositories, or through apps that send this information in clear-text format on the client side. Your primary task this week will be to ensure that your project is designed in a way that allows authorised users to access your application in a way that doesn't expose keys to malicious users. Your secondary goal is to understand how and why OAuth2 allows you to limit access to specific resources, and the design implications of this. Since we're using the github API, the flexibility to define access conditions is restricted by the different kind of access tokens that can be generated. Application design can further reduce the use of tokens, but negotiating between authentication and design is your job this week: what is the minimum level of access that you need to allow for your application to work?
 - Visualising OAuth flow: check out [the process here](https://www.gliffy.com/publish/3960679/)
 - Read up on the IETF's [OAuth2 framework](http://tools.ietf.org/html/rfc6749), at least section 1, preferably sections 1-7. Can you summarise each section?
 - Have a look at the code for OAuth2's [toolkit for NodeJS here](https://github.com/t1msh/node-oauth20-provider). Can you trace the OAuth2 flow through this code?
 - Read up on [OAuth via Github](https://developer.github.com/v3/oauth/). You should understand how to:
  - Register an application
  - Generate personal access tokens
  - The range of resources available via Github
 - Also read the OAuth API for [Github](https://developer.github.com/v3/oauth_authorizations/)
 - Look at the code for a node implementation of OAuth2, for example [Node-ouath2-server](https://github.com/thomseddon/node-oauth2-server)
 
###Github (Unauthenticated)

* [ ] What are rate limits and what can you do as an unauthenticated user?
* [ ] How can you tell if a request is not authenticated by server responses?

Take [Github API](https://developer.github.com/v3/) as your starting point. The primary aim of your research should be to understand what can be done with github's API without authenticating users. Working with github and OAuth2 for the first time is often confusing due to the fact that it is easy to make requests to github that aren't authenticated without realising. You should aim, therefore, to become the go-to person for understanding what is happening when authentication fails, as well as be able to identify unauthenticated calls. Moreover, while rate limits exist for authenticated requests, they are unlikely to affect small scale projects that are well designed. Unauthenticated requests are far more limited, therefore you should make a particular effort to familiarise yourself with github's request limits, as well as means of extending or resetting them.
 - Read through the schema
 - What are the rate limits for authenticated and unauthenticated requests?
 - How can you check your rate limit status?
 - What is the search API's limit? Why is it different?
 - Use curl from the command line to experiment with the different types of REST API calls
 - List out the API calls unauthenticated users are permitted to make.
 - Force client errors on possible API calls
 - Explore using conditional requests that do not affect the rate limit
 - Read through and understand all the different types of authentication errors. Try making as many unauthenticated requests for information that requires authentication so that you have experience reading through and understanding errors that result from authentication rejection.
 
###Github (Authenticated)

* [ ] How do you authenticate a user using Github's API? What are the different methods?
* [ ] How flexible is Github's authentication? What can't you do that you could do with your own hosted git?

Again, take [Github API](https://developer.github.com/v3/) as your starting point. Your primary aim is to understand what can be done with authentication on github. You should understand how to generate access tokens, as well as the reason for doing so. 
 - Work through the [basics of authentication on github](https://developer.github.com/guides/basics-of-authentication/)
 - Check out this [guide to using CURL for authentication](https://blogs.infosupport.com/accessing-githubs-rest-api-with-curl/) as it will help you play with making authenticated requests to the github API
 - Read through [adjusting token scopes](https://developer.github.com/v3/oauth/#scopes)
 - Research Github's [events API](https://developer.github.com/v3/activity/events/), pay particular attention to understanding the _list events for organization_ GET request, which can be used to access organization events on behalf of a user.
 - Research the issues API: how could you create an issue on a github repo without using the website?
 - Experiment with adjusting the pagination of an API call that returns more than 30 items 
 - Optional: force client errors as detailed in the schema as an authenticated user
 
###Git internals

* [ ] How does the git stash work? Why might you use it?
* [ ] What do pipes do in BASH scripts? How can they be used to save data or to transfer it?

Take [git internals](https://git-scm.com/book/en/v1/Git-Internals) as your starting point. The primary aim of your research is to get as deep inside the workings of git as possible. Ideally, you should be able to read and understand all the automated text that comes up every time you make a commit in git. You will learn more about git than you need to know to contribute to projects, but by doing so, you'll be able to tell the rest of your team what is going on under the hood. 
 - Read through [10.1 Plumbing and Porcelain](https://git-scm.com/book/en/v1/Git-Internals-Plumbing-and-Porcelain)
 - Work through [10.2 Git Objects](https://git-scm.com/book/en/v1/Git-Internals-Git-Objects)
 - Read 10.3-10.5 of the git reference, and refresh your memory of [Git Branches](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
 - Read up on the [git stash command](https://git-scm.com/book/en/v1/Git-Tools-Stashing) with particular attention to options like [pop, clear and drop](https://git-scm.com/book/en/v1/Git-Tools-Stashing).
 - Return to one of your old projects and use what you've learned to navigate through the project from the command line. Practice switching branches, using git logs etc
 - Read through sections 1-4 of the intro to [BASH programming](http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html)
 - Practise outputting git logs to files
 - Check out [8.1 Git configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration). Once you combine a working knowledge of git internals and basic shell scripting, you can start to do some pretty powerful things!
  - [Automating git pulls](http://cgrinaldi.github.io/2015/02/24/automating-git-pull/)
  - [Pulling logs from each branch of a repo with one command](http://stackoverflow.com/questions/3846380/how-to-iterate-through-all-git-branches-using-bash-script)