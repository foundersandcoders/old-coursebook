# Git Command Line Documentation

## Description

To write a README for Git in the command line.

## Usage

Training notes for Git Command Line.

## Contributing

Gethin and Matt

## Introduction

Purpose of this readme is to introduce some core concepts of Git on the command line and provide a glossary of commands and their usage.

### *Repository (repo)*

Simply put, this is your project folder. This repository can be located locally (in your file system on your computer), or remotely (on Github). Either way, it is the same repository.


####Status

List the files you've changed and those you still need to add or commit:

Get in the habit after each command to use `git status`.

```
git status
```

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
git clone https://github.com/NataliaLKB/learn-git-basics.git
```

##### *Pull*

Updates your local repository with any changes made to the repository on github.

```
git pull
```

### *Commit*


A way of saving your code at different points along the project. Unlike many tools you may have used however, all commits are saved. This creates a project history and a way to track changes.

####Add

The 'add' command adds a file to the staging area (the staging area is the collection the files which are ready to commit).
It is the step to take before committing the changes to the local *Repository*.
```
git add filename
```
or, if you want to add all your changes to the staging area:
```
git add .
```

####Commit

The 'commit' commands takes all the files that you've added to the staging area, and commits them to the local repository. They are not yet in your remote repository (at github.com).
```
git commit -m "Your commit message"
```
The commit message makes it possible to track what has changed in each commit.

####Push
To send your changes to your remote repository, you must use the 'push' command.
```
git push origin branchname
```
Here you are pushing your changes from your local branch to your remote branch.

### *Branches*

As you work on a git repo the first branch you are on is usually the default branch. This is often called `master`. If you start working on a section of the website (say the footer styling), it is best practise to create your own branch for that feature. Creating your own branch is like taking a copy of `master` and renaming it. When you commit, they will now be on that new branch only.

#####Branch

When there are other branches in your repo the green branch is the current one you are on.

List all the branches in your repo, and also tell you what branch you're currently in:

```
git branch
```

#####Checkout

Switch from one branch to another:
'''
git checkout <branchname>
'''

#####Merge (add commit message/ exit vim)

To merge a different branch into your active branch:
'''
git merge <branchname>
'''

#####Closing Issues Using Pull Requests

It's possible to close an issue from a commit, but some issues take more work than a single commit to close. That's why you can close an issue from a Pull Request. All you have to do is include the special keyword syntax (eg. "fixes #5") in the body of your Pull Request. Commands can also be added to the commit messages. For Example, add the following information to the Pull Request messages:

```
Resolve #18 (Issue number)

Pull Request #19: blah (Add pending fix before merging)
```

#####Keywords for closing issues

The full range of commands that can be added.

```
close
closes
closed
fix
fixes
fixed
resolve
resolves
resolved
```

#####Closing an issue in a different repository

To close an issue in another repository, use the username/repository#issue_number syntax, as described in "Writing on GitHub".

For example, including
```
Closes example_user/example_repo#76
```

 will close the referenced issue in that repository, provided you have push access to that repository.

#####Closing multiple issues

To close multiple issues, preface each issue reference with one of the above keywords.For example,

```
This closes #34, closes #23, and closes example_user/example_repo#42
```

 would close issues #34 and #23 in the same repository, and issue #42 in the "example_user/example_repo" repository.
