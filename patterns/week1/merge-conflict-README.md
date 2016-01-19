# Dealing with Merge Conflicts

<img src="https://cloud.githubusercontent.com/assets/1287388/12421239/1cfaade0-beb9-11e5-9420-59c5fc684f66.jpg" width="50%">

## Why me?  
You may find yourself dealing with a merge conflict if
someone decided not to follow proper git-flow. If the
branch you are attempting to merge with has changes which
clash with the changes you made, a conflict can occur.
Anytime you and another person make changes to the same
part of the same file, Git won't know which is correct
and will cause a conflict.

## How can I fix it?  
[Natalia's guide](https://github.com/NataliaLKB/learn-git-basics#conflicts)
is a key resource that shows step-by-step how to fix a
merge conflict with examples.
Some key commands that are used in resolving conflicts
are:  
`git branch -a` - this checks all branches on the repo.  
`git checkout branchname` - the `branchname` is the
branch that has conflicts with master.  
`git diff master` - this shows the differences between
the current branch and master. You can edit this until
it looks how you want. The section labelled `HEAD` is
from your current branch, and the section labelled
`master` is from the master branch. Be sure to delete
the extra lines.

![](https://github.com/NataliaLKB/learn-git-basics/raw/master/img/merge-conflict.png)

You can then add, commit, and push as you normally
would and the conflict should be resolved.
