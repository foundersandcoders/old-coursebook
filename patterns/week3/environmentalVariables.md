## Environmental Variables
You can avoid committing your private keys, passwords or other sensitive details to GitHub by storing them as environment variables. Environmental variables are stored in a .env file. All entries in the .env file are exported as environmental variables available as keys in the process.env object.

## Env2 Module
The env2 module allows you to store your environment variables in an .env file which you can then call upon in your JavaScript files.

First make sure you have a package.json by typing 

```npm init```

Then to install the env2 module 

```npm install env2 --save```

Create a config.env file and add any variables that you want hidden e.g. passwords and API keys like so:
```
Password=Ilovecoding
API=123456789
```

Please note there can be **no spaces** in the config.env file.

You need to make sure your config.env file is placed in a .gitignore file. You can do this by typing 

```echo 'config.env' >> .gitignore```

You can then call these hidden environmental variables in your JavaScript files using:
```
require('env2')('config.env');    // loads all entries into process.env

console.log(process.env.Password);
console.log(process.env.API);
```

Alternatively you can store your files in an env.json configuration file.

Further info on env2 can be found [here](https://github.com/dwyl/learn-environment-variables).
