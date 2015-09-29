##First what are git-Hooks ? 

Git hooks are scripts that Git executes before or after events such as: commit, push, and receive. Git hooks are a built-in feature - no need to download anything. Git hooks are run locally.

These hook scripts are only limited by a developer's imagination. Some example hook scripts include:

pre-commit: Check the commit message for spelling errors.
pre-receive: Enforce project coding standards.
post-commit: Email/SMS team members of a new commit.
post-receive: Push the code to production.


##Okay so what is a  Pre-commit Hook? 

Pre-commit is a pre-commit hook installer for git. It will ensure that your npm test (or other specified scripts) passes before you can commit your changes. This is all conveniently configured in your package.json. There are a number of pre-commit modules we are going to look at 'pre-commit'.

##First let's set it up! 

Create a project folder and point to your folder in command line. Initialsie Repo using ```git init``to create a Repo.

In your working directory run ```npm init``` this will create your package.json file and add your node_modules to the directory. 

You have to install 'pre-commits' in each project folder before you start your project and after you've created your Repo.

```npm install pre-commit --save-dev```

Once you have installed the pre-commit modules this should appear in your package.json object like this: 

``` "devDependencies": {
    "pre-commit": "^1.1.1"
  }
```

If you do not want to use a pre-commit then you can still force a commit by telling git to skip the pre-commit hooks by simply committing using ```--no-verify```	


Define your scripts in the package.json file (In this example we are using, Istanbul for coverage, jshint, and tape).You also need to create an pre-commit array of the scripts that you need to run. Here is an example of this: 


'''{
  "name": "learn-pre-commit",
  "version": "1.0.0",
  "description": "Node.js pre-commit tutorial",
  "repository": {
    "type": "git",
    "url": "https://github.com/nelsonic/learn-pre-commit"
  },
  "devDependencies": {
    "istanbul": "^0.3.2",
    "pre-commit": "0.0.9",
    "tape": "^3.0.1"
  },
  "scripts": {
    "test": "tape ./test/*.js",
    "coverage": "istanbul cover tape ./test/*.js && istanbul check-coverage --statements 100 --functions 100 --lines 100 --branches 100",
    "jshint": "jshint -c .jshintrc --exclude-path .gitignore .",

     },
  "pre-commit": [
    "jshint",
    "coverage"
  ]
}'''

 
Pre-commit will now run everytime before you commit providing that you have pre-installed the relevant modules.
