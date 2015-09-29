# What is Heroku?

- It's a cloud-based, scalable server.
- Allows you to easily manage the deployment of your app 
- It's free (for 1 Dyno) - great for testing, but insufficient to run a business on.

# What is Heroku used for?

- Instant Deployment with Git push 
- Processes scaling - independent scaling for each component of your app without affecting functionality and performance
- Isolation - each process (aka dyno) is completely isolated from each other.
- Performance is good - e.g. simple web application written in node.js can handle around 60 - 70 requests per second.
- Full Logging and Visibility - easy access to all logging output using:

```shell
heroku logs
```
