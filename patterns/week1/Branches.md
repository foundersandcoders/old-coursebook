A branch is a thing that points from the original code you've copied/cloned to
the new thing that you're working on.


A local branch on Git is one that you can only see on your machine.
A remote branch is what your local branch becomes when you push it to origin.
This means every other user can access it.

GitBranch related commands

View: If you want to see all the branches that exist including those
not in our own workspace.

<pre><code> git branch -a </code></pre>

Create: To create a branch, type -

<pre></code> git checkout -b 'my_new_branch' </code></pre>

Note, this both creates the new branch and 'checks it out' (allows you to move
into it so you can work on it)

It's the quicker version of this:

<pre></code> git branch 'my_new_branch'</code></pre>
<pre></code> git checkout 'my_new_branch'</code></pre>

Regularly check which branch that you're on as you might accidentally add your
changes to master instead of your remote branch. You do this by typing:

<<pre></code> git branch </code></pre>

When you're ready to create a remote version of your branch so other people
can access it you type:

<pre></code> git push origin 'my_new_branch' </code></pre>

This is also how you add any changes online that you've made locally when you're
working on the file later on.

Make sure you're never pushing to the master as this will overwrite it for other
users.

Best practices for using branching:

- Everytime a developer needs to start working on a new feature they should create
a branch for the feature. This means that they can work on the new feature
without comprimising the code of a previous branch that others are working from.

- It's like a box that you can work in without messing things up for anyone else.
Then when it's ready and bug free you can merge it back to branch it branched from.

- You should always branch if:
- You're about to make a really big change that might disrupt everything.
- You're about to make make a change that is just an option/ something that might
not be used.
- You want to try something that you're 90% sure won't work and may break
everything. A branch is your safe box to break things you can delete it later if
it doesn't work.

To delete a branch and when to do it:

You can delete your branch locally by typing

<pre></code> git branch -d branchname </code></pre>

or delete it on the server (remotely) so it's not in the way of other users
by typing

<pre><code> git push origin --delete branch_name </code><pre>

???If any of your changes are unmerged (not added to the larger branch before yours)
then git will tell you and won't delete it. ????
