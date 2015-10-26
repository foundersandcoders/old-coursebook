# Git internals 
### Plumbing & Porcelain

Porcelain - user friendly commands eg. git branch and commands we have all been using over the past 6 weeks so far.

Plumbing - commands that do a lot of things under the hood eg. ls-remote, ls-files, rev-parse, give you access to inner workings of git, help demonstrate how and why git does what it does.


### .git directory

1. Find an old project repo and move into the folder locally
2. In the root folder move into the `.git` folder
3. Now run `ls -F1` and you should see the below (without the comments)

``` markdown
$ ls -F1
HEAD - points to the branch you currently have checked out
config* - contains project specific config options
description - description that you assigned to your repo
hooks/ - contains scripts that run before or after events eg. commits/pushes
info/ - contains global exclude file which differs from .gitignore in that any files excluded in this way are local and not excluded for other people working on the project.
objects/ - stores all the content for your database (encoded somewhow)
refs/ - stores pointers into commit objects in the data. (THIS SMALL SECTION NEEDS ATTENTION)
```


### Git Objects

Git stores everything in a database as key-value pairs (like Redis). You may see this being called a Content Addressable Filesystem. You can view this database in the `objects/` folder mentioned above.

When you create different versions of work in Git (eg. branches, commits) Git saves the contents of each file as a hash in the objects folder so it can access the different data when you need it. If you follow [this tutorial](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects) you will learn the underlying (Plumbing) commands that run when we call our Porcelain commands that we are used to.

### Git Stash Tutorial

Git stash allows you to temporarily store your unstaged changes in a stack so that you can move between branches without committing your changes.

`git stash` - adds your current unstages changes to the stack

`git stash pop` - takes the most recent stash from the stack and applies it to your work, then removes it from the stack

`git stash drop` - removes a stash from the stack without applying it to your work

`git stash clear` - clears the whole stack. *Use with caution*



[Here's](https://git-scm.com/docs/git-stash) a really good description of STASH commands

[Here's](https://git-scm.com/book/en/v1/Git-Tools-Stashing) a tutorial on how to use them


### Little bit'a BASH

Open up you terminal, and do the following:

**Hello world**

```bash
echo hello world
```

You have successfully written a BASH hello world app. Well done.

**Greater than**

&gt; is a redirection operator. It takes an input, and writes it to a file.

Open a git repository on your computer, and execute the following

```bash
git logs > logsalot.txt
```

This command runs *git logs* and writes its output to the file logsalot.txt

**Piping**

Now type this into your terminal

```bash
echo six | sed -e "s/[aeio]/e/g"
```

| is another redirection operator. It takes the output of a command as the input to another command.

This takes the string 'six', pipes it into *sed* which is a command line text editor, which replaces all vowels with 'e'.

*NB. 's/abc/xyz' is a sed command, meaning substitute abc with xyz*


**Standard--**  (THIS SMALL SECTION NEEDS ATTENTION)

stdin means standard in.
stdout means standard out.
stderr means standard error.

When running commands from the command line, for example

```bash
   ls -l | grep "\.txt$"
```


#### References

You can create powerful programs in BASH, using for and while loops, running any command you can access from the terminal. Do read into it at the following references:


['sed commands'](http://www.grymoire.com/Unix/Sed.html)
['Into to BASH programming'](http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html)
