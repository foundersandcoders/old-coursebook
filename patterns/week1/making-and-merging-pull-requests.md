
#Making and merging pull requests



Pull requests let you tell others about changes you've pushed to a repository on GitHub.
Don’t not do your own pull requests, this is very bad practice as you won’t spot the mistakes (similar to proofing your own work).


This allows your team to review your code and suggest changes to it.


###To start a pull request 
1. First make sure your local master branch is up to date with the remote master by typing this into your terminal:
```git pull origin master```
2. Checkout back to your own branch and merge with the master branch to make sure you have no conflicts: ```git merge master```
3. Now you need to push your changes up to github: ```git push origin yourBranchName```
4. On github go to your branch and click "New pull request"
5. Someone else in your team can now review the changes
6. Once they are happy with the changes they can click to merge with master.


### Links
https://help.github.com/articles/using-pull-requests/ github tutorial using just github.com

http://git-scm.com/docs/git-request-pull
