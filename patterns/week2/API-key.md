#API Keys

API's often require a key to access them. This allows the API owner to maintain some control and easily monitor their API.

This is done for:
* security
* monitoring / analytics
* Paid access

##Example
APIs may look different from different providers, but here is an example of what one might look like:
<img src='https://developers.google.com/google-apps/tasks/images/APIs_Console_API_Key.png'> 

Depending on what you want to do with the API, you may need a different type of key. Youtube for example has two levels of API keys. Every request must either specify an API key (with the key parameter) or provide an OAuth 2.0 token. Your API key is available in the API console's API Access pane for your project.

A link to a how to guide for youtubes API: [you tube api] https://developers.google.com/youtube/v3/getting-started 

##Best Practices for generating API keys
* It is recommeneded for you to use API keys if you have an API (for security and data reasons)
* Name your key descriptively
* Give each intergration (user) it's own API key, and assign labels for each key. So each key is unique. As an administrator this allows you to disable a key if it has been compromised without disabling access to all of your other intergrations (users).
* In addition, you may want to segment access to different data, for example on Nestoria.co.uk (property site) has one API for average house prices, and another API for listing searches. Again this allows you greater control of your APIs.



