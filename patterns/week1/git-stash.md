# Git stash 

## What?

A git command used to clean your working directory and enable you to move to the HEAD of your branch. 'HEAD' is an arbitrary word that points to the top of your current working branch.  

**git stash** temporarily stores your uncommitted changes in a 'stash' stack, demonstrated further down the page.  

## Why? 

You may find yourself in a situation where you want to change branches quickly. You may:
 * Have just remembered something you want to build at the top of the branch
 * Have been asked to fix a critical bug
 * Want to work on other branches and not commit messy changes 
 
You could clean your working directory with:
 
> git reset --hard 

Which would delete all the code you've been working on (it's *unlikely* you'd want to do that!) 

Or, you could create a new branch and commit there. However your code might be quite messy and disorganised so you don't want to commit yet, as we covered above.

The third option is to use **git stash**! 

## How? 

Let's have a look at how it works.

This is the process of cleaning your directory through the command line:

> git status  
  On branch master  
  Changes to be committed:  
  (use "git reset HEAD <file>..." to unstage)  
    modified:   index.html  
  Changes not staged for commit:    
  (use "git add <file>..." to update what will be committed)  
    modified:   lib/simplegit.rb

This **git status** command shows us there are still changes to be committed and changes that are not staged for commit.
If we use our snazzy **git stash** command: 

> git stash
  Saved working directory and index state \  
    "WIP on master: 049d078 added the index file"  
  HEAD is now at 049d078 added the index file  
  (To restore them type "git stash apply")

Now, after we use **git status** again we should see something else:

> git status  
  On branch master  
  nothing to commit, working directory clean  

Ta-da! Now our working directory is clean and we can move around as we please.

### Stash Commands 

When you use **git stash** over and over again, your stashes are stored on top of each other in a stack like so:
 
![Stash stack](https://cms-assets.tutsplus.com/uploads/users/585/posts/22988/image/git-stash-stack.png)

So we can check our previous stashes using **git stash list**:

>  git stash list  
  stash@{0}: WIP on master: 049d078 added the index file  
  stash@{1}: WIP on master: c264051 Revert "added file_size"  
  stash@{2}: WIP on master: 21d80a5 added number to log

They are ordered in indexes, with 0 being your most recent stashing.

You can reapply previous stashes with the command **git stash apply**. You can be slightly more specific by using the indexes with **git stash apply stash@{2}**

> git stash apply  
  On branch master  
  Changes not staged for commit:  
    (use "git add <file>..." to update what will be committed)  
       modified:   index.html  
       modified:   lib/simplegit.rb

**git stash branch** is a good method to use if you run into any problems reapplying your stash. If the **apply** tries to modify a file that you’ve since modified, you’ll get a merge conflict and will have to try to resolve it. Use **git stash branch** to create a new branch for you, check out the commit you were on when you stashed your work, reapply your work there, and then drop the stash if it applies successfully:

> git stash branch testchanges  
  Switched to a new branch "testchanges"  
  On branch testchanges  
  Changes to be committed:  
    (use "git reset HEAD <file>..." to unstage)  
       modified:   index.html  
  Changes not staged for commit:  
    (use "git add <file>..." to update what will be committed)  
       modified:   lib/simplegit.rb  
  Dropped refs/stash@{0} (f0dfc4d5dc332d1cee34a634182e168c4efc3359)

**git stash pop** is a bit of a dangerous command to use, but it is used for instantly reapplying your previous stash without reviewing it. It will then remove that stash from the stack. It's not a recommended command. Read more [here](https://codingkilledthecat.wordpress.com/2012/04/27/git-stash-pop-considered-harmful/). 

**git stash drop** can be made more specific e.g. **git stash drop stash@{1}** and is used to delete a stash from the stack. 

**git stash clear** will clear the whole stack! 

**NOTE:** Some people *do* prefer committing messy working directories to a branch instead of using **git stash**, but we'll let you decide that for yourself!   



