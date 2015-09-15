# Git Command Line Documentation

TODO: Write a project description

## Usage

Training notes for Git Command Line

## Contributing

## Introduction

Purpose of this readme is to introduce some core concepts of Git on the command line and provide a glossary of commands and their usage.

Structure: Concept 
Command
Explanation

### *Repository (repo)*

####Status

List the files you've changed and those you still need to add or commit:

Get in the habit after each command to use `git status`.

```
git status
````

You should only see `master` which is the default branch in this repo.




####Concept

Simply put, this is your project folder. This repository can be located locally (in your file system on your computer), or remotely (on Github). Either way, it is the same repository.

####Commands

#####Fork

Forking creates a full copy of the repository in your own github profile.

Use the button in your github profile.

![fork button on github](./img/fork.png)

#####Clone

Cloning the forked repository creates a local copy of a repository.

![where to copy url on github](./img/git-clone.png)
```
git clone <repository web address>
```
Example: 
```
git clone https://github.com/NataliaLKB/learn-git-basics.git ```

#####Pull

Updates your local repository with any changes made to the repository on github.

```
git pull 
```

### *Commit*

####Concept

A way of saving your code at different points along the project. Unlike many tools you may have used however, all commits are saved. This creates a project history and a way to track changes.

####Commands

Add
commit
Push


### *Branches*

####Concept

As you work on a git repo the first branch you are on is usually the default branch. This is often called `master`. If you start working on a section of the website (say the footer styling), it is best practise to create your own branch for that feature. Creating your own branch is like taking a copy of `master` and renaming it. When you commit, they will now be on that new branch only.


####Commands

#####Branch

When there are other branches in your repo the green branch is the current one you are on.

List all the branches in your repo, and also tell you what branch you're currently in:

```
git branch
```

#####Checkout

Switch from one branch to another:	
git checkout <branchname>

#####Merge (add commit message/ exit vim)

To merge a different branch into your active branch:	
git merge <branchname>


## Credits

TODO: Write credits

## License

TODO: Write license