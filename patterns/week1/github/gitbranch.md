Crucial reference:
https://www.atlassian.com/git/tutorials/using-branches/git-branch

What is Master?
In github when you first create a repository all the code within that is now in the 'master'. It's a rule that everything in master is deployable and so only quality controlled, peer-reviewed code should make it into the master branch. While you are adding features or changing code this should all be done on an individual branch that can be merged into master later after being checking by your team.

So what are branches?
When making any changes it is essential that you do not work directly onto master. To get around this you should create your own branch, making sure to name it something that is relevant. For example if I'm adding a new GPS feature to my app I might call my branch 'feature-gps'.   
<img src="https://www.atlassian.com/git/images/tutorials/collaborating/using-branches/01.svg" width="600">

This also allows multiple team members to work on their own separate branches for individual features and merge them into master when they are ready. Having branches that are for specific pieces of work also reduces the likelyhood of merge conflicts.

Great, how do I a branch?
```
git branch // list branches
git branch <branchname> // create a new branch
git checkout <branchname> // Actually switch to your branch
```
git checkout allows you to switch between branches in your code.
You should now work on this branch, committing to the branch as usual until you are ready to push your changes to the master

How do I commit again?
```git commit -m 'A useful commit message'
```

Wait, some of my files don't seem to be commiting?
Your files might still be untracked, you can check this out with
```git status
```

You can start tracking them in a few ways
```git add * #Will add all files in a folder
git add <filename> # will add specific files
```
then you need to commit them, like in the above example

Cool, my super awesome feature is finished, how do i get it into master?
First you need to push your branch, then create a pull request so your team can review your changes and comment on your proposed code.
![alt pull-request](https://www.atlassian.com/git/images/tutorials/collaborating/making-a-pull-request/02.svg)
```git push --set-upstream origin <branchname>
```
Then you need to create a pull request, which is fully explained <a href=https://yangsu.github.io/pull-request-tutorial/> here </a>
