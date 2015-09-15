
#Making and merging pull requests



Pull requests let you tell others about changes you've pushed to a repository on GitHub.
Don’t not do your own pull requests, this is very bad practice as you won’t spot the mistakes (similar to proofing your own work).


This allows your team to review your code and suggest changes to it.


###To start a pull request 
1. log in to github.com
2. fork an existing repository, make changes, commit & push the changes.
3. navigate to your repository on github.com
4. go to the branch which contains the changes 
5. click “New pull request”  and then "create pull request"
For the person who will review your code:
6. go to terminal type 
 *git pull origin branch name* 
(make sure you are in the correct directory for git)
7. Now you have an up to date version of the changes which have been made to the file on your computer.
8. Review changes. Once you are happy with the changes you are ready to merge the branch into master


##Merging with Master


On github.com,  on your repository, on the right sidebar, you should see that you now have a pull request.

If you know there are no conflicts you can merge the pull request remotely on github.com, otherwise you will need to pull down and resolve conflicts locally.

To merge on Github:
1. click on pull requests
2. click in to your specific pull request

To merge locally:
1. git checkout branch name
2. git merge origin master


### Links
https://help.github.com/articles/using-pull-requests/ github tutorial using just github.com

http://git-scm.com/docs/git-request-pull
