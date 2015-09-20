# How to uses Git Branches

**A branch is a device that points from the files of original code you cloned to
the new box where you're working on your own edits.**


A local branch on Git is one that you can only see on your machine.
A remote branch is what your local branch becomes when you push it to origin.
This means every other user of your repository can access it.

### Git Branch and related commands

##### View Branch
If you want to view the branches that you can access locally on your computer enter the command:

<pre><code> git branch </code></pre>

This will show you the branch you're currently on marked in green with a star next to it. The branches you can move onto will be marked white.

If you want to see all the branches that exist in your repository and not just those on your local computer enter the command:

<pre><code> git branch -a </code></pre>

This will appear as above but other branches that have been pushed to your repository by others users will be marked in red.


##### Create Branch

In order to create a branch enter the command below into the console.

<pre></code> git checkout -b 'my_new_branch' </code></pre>

Note that this both creates your new branch and 'checks it out' which allows you to move into the branch and start working on it.

It's a shortcut to entering the two commands below:

<pre></code> git branch 'my_new_branch'
git checkout 'my_new_branch'</code></pre>

You should regularly check which branch you're on to prevent yourself adding files or changes to the master instead of your branch by typing the git branch command.

When you're ready to create a remote version of your branch so other people
can access it you type:

<pre></code> git push origin 'my_new_branch' </code></pre>

This is also how you add any changes online that you've made locally when you're
working on the file later on.

Make sure you're never pushing to the master as this will overwrite it for other
users.

#### Best practices for using branching:

Everytime a developer needs to start working on a new feature they should create
a branch for the feature. This means that they can work on the new feature
without comprimising the code of a previous branch that others are working from.

It's like a box that you can work in without messing things up for anyone else.
Then when it's ready and bug free you can merge it back to branch it branched from.

You should always branch if:
- You're about to make a really big change that might disrupt everything.
- You're about to make make a change that is just an option/ something that might
not be used.
- You want to try something that you're 90% sure won't work and may break
everything.

##### To delete a branch

You can delete your branch locally by entering the following command where mybranch is the name of the branch you'd like to delete:

<pre></code> git branch -d mybranch </code></pre>

If you have unmerged changes you'll have to enter the command again to confirm you really do want to delete it.

You can delete it on the server (remotely) so it's not in the way of other users
by typing

<pre><code> git push origin --delete branchname </code><pre>

You can also delete the branches directly from git hub once you've merged the contents with the previous branch.
