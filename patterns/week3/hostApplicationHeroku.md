#How to Host an Application on Heroku?

Heroku Development Centre provide a helpful walkthrough. Found here:

https://devcenter.heroku.com/articles/getting-started-with-nodejs

This tutorial is comprehensive and should be followed. However there were various difficulties with this and these are pointed out below.

First sign up for a Heroku account.

###Setup

Download Heroku toolbelt.
Use the Heroku command to login and authenticate.

###Prepare the App

Git clone the app that Heroku provides.

Change the directory.

Find the name of the app on the Heroku website when logged in to your Heroku account. This would be found on your Heroku dashboard.

Heroku commands may not work, particularly on Crouton. If so sudo -s may be necessary on Crouton to run each of the different parts.


###View Logs

Logs are streams of time-ordered events aggregated from the output of your app.

###Define the Procfile

Procfile is mechanism for declaring what commands are run by your applications dynos on the Heroku platform.

###Config Variables

At run-time config vars are exposed as environment variables to the application.

####Deleting Apps

On the dashboard one can delete unwanted apps.

##Git hub Tutorial

https://github.com/Neats29/Learn-Heroku

The Neats29 github tutorial was helpful to understand Heroku. The explanation of a Dyno is one example of this. The tutorial simplified this a great deal making things difficult to follow.

References:
http://nieldlr.com/2012/03/the-really-absolute-beginners-guide-to-host-node-js-on-heroku/
https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction

