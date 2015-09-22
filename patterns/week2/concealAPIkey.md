#Concealing an API key

An application programming interface key (API key) is a code passed in by computer programs calling an API (application programming interface) to identify the calling program, its developer, or its user to the Web site.


##The problem

As you begin to integrate third-party services into any application you’re building, you’ll probably need a set of “keys to the castle”, the API key and/or secret to tell this third-party service you are who you say you are.

As soon as you publish this information to GitHub or some other repositories your personal API key would be freely available to anyone who is looking.

So before you pushing from your local computer the API key needs to be secured/concealed.

##How?

###2 Ways

####\#1 bash configuration file

In order to conceal your API keys you need to find your configuration file for your terminal/bash. At the moment the name of the configuratil file seems to be a contencious topic. From the research we have carried out we believe, depending on which operating software you are using, the file you need to update varies:

- MacOSX: .bash_profile
[Creating .bash_profile manually](http://redfinsolutions.com/blog/creating-bashprofile-your-mac)
- Unix/Linux: .profile & .bashrc
[Please read here for instructions](http://www.joshstaiger.org/archives/2005/07/bash_profile_vs.html)

*NB. We will be using .bash_profile for reference*

To set environment variables locally, you can place them inside of your .bash_profile file. This file is a collection of settings you’d like to use when using bash, the default terminal access application.

Within your .bash_profile you need to insert the API you wish to conceal.

eg. Twitter
```Javascript
export TWITTER_KEY = ljahs84d7b6skdbv3sdjkbff23jk
```

Once you save this file you either need to source it by using:

```Javascript
source ~/.bash_profile
```

In any new session that you open (new terminal windows), the environment variable will be sourced automatically because ~/.bash_profile is sourced by default when a new session is open.

When writing your code you can now call TWITTER_KEY instead of referencing your full API Key in your code.

```Javascript
ENV['TWITTER_KEY']
```

####\#2 environment variable file

Another way is by creating a local environment variable file (.env)

.env
```Javascript
  # some env variables

  FOO=foo1
  BAR=bar1
  BAZ=1
  QUX=
  # QUUX=
```

and calling that within your javascript file.

index.js
```Javascript

var assert = require('assert');
  var env = require('node-env-file');

 //redefining the variable 'FOO' from 'foo1' to 'defaultfoo'


  process.env.FOO = "defaultfoo";

  // Load any undefined ENV variables from a specified file.

  env(__dirname + '/.env');
  assert.equal(process.env.FOO, "defaultfoo");
  assert.equal(process.env.BAR, "bar1");
  assert.equal(process.env.BAZ, "1");
  assert.equal(process.env.QUX, "");
  assert.equal(process.env.QUUX, undefined);
```

This method allows you to pass your environment variables between a team since you can send the .env files. Or simultaneously access/edit them using a private Google Doc.


[Best practices for securely using API keys](https://developers.google.com/console/help/new/#apikeybestpractices)

[Environment variable file](https://www.npmjs.com/package/node-env-file)

[Bash configuration file](http://nycda.com/blog/using-environment-variables-to-safely-store-api-credentials/)
