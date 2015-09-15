
#Making and merging pull requests



Pull requests let you tell others about changes you've pushed to a repository on GitHub.
Don’t not do your own pull requests, this is very bad practice as you won’t spot the mistakes (similar to proofing your own work).


This allows your team to review you code and suggest changes to it.


###To start a pull request 
1. log in to github.com
2. fork an existing repository, make changes, commit & push the changes.
3. Navigate to your repository on github.com
4. go to the branch which contains the changes 
5. click “New pull request”  and create pull request
6. go to terminal type 
 *git pull branch name* 
(make sure you are in the correct directory for git)
(this should not be done by the author of the code).
7. Now you have an up today version of the changes which have been made to the file.
8. Review changes. once you are happy with the changes you are ready to merge the the branch in to master


### links
https://help.github.com/articles/using-pull-requests/ github tutorial using just github.com

http://git-scm.com/docs/git-request-pull



##Merging


On github.com,  on the right sidebar, underneath code, you should see that you now have a pull request.

1. click on pull requests
2. click in in to your specific pull request.
If there are no conflicts you can merge the pull request remotely on github.com, other you will need to pull down and resolve conflicts locally.

just keep clicking through.


###Conflict
Conflicts occur when the same file has been edited in two different branches and you tried to merge the two branches together.
This needs to be resolved locally.

in your text editor, it will show up where the conflict occurs (notified by <<<<<<<<<<<<<<< HEAD and =================) you need to remove part of the conflict so that it no longer exists. 



###To resolve locally
Pull down the file from github.com
*git pull origin branch-name*


