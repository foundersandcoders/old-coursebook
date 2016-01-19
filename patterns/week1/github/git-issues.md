<h3><a href='https://guides.github.com/features/issues/'>Github issue tracker</a></h3>

Issues are a great way to keep track of tasks, enhancements, and bugs for your projects. They’re kind of like email—except they can be shared and discussed with the rest of your team. Most software projects have a bug tracker of some kind. GitHub’s tracker is called Issues, and has its own section in every repository.

<h3> Why use an issue tracker? </h3>
Software is never finished,you can never test it on every device with every circumstance, so sometimes things go wrong.
An issue tracker is a great way for people to report bugs and submit fixes to those bugs if they have a solution.

Milestones allow you to plan features in advance, for example maybe your getting ready for a Beta launch and you still have features to add. You would setup a 'Beta Launch' milestone, where all the bugs that must be fixed before launch will be grouped. You can assign a bug to yourself when you being working on it, this helps you keep track of your workload and allows your team mates to know which bugs are currently being worked on.

You can also use labels to organise different types of issues, you can then filter be label when searching.

<h3> Mentions and References </h3>

@mentions are the way that we reference other GitHub users inside of GitHub issues. Inside of the description or any comment of the issue, include the @username of another GitHub user to send them a notification. This works very similar to how Twitter uses @mentions.

Often times issues are dependent on other issues, or at least relate to them and you’d like to connect the two. You can reference issues by typing in a hashtag plus the issue number.

Hey @kneath, I think the problem started in #42
When you do this, we’ll create an event inside of issue #42.

<h3><a href='https://help.github.com/articles/creating-an-issue/'>Creating an Issue</a></h3>
Following the link for a very simple guide on creating issues. Please be sure to be as specific as possible, include what device you are running the code on and under what circumstances the bug occurs. It's even better if you can reproduce the bug and give a description of steps to take to make the bug happened again. Finally if you think you can fix it, submit a change and make a pull request!

<h3> Closing an issue from your commit </h3>
If you know that you have resolved an issue with one of your commits you can automatically close it with your commit message!
```
This closes issue #33 and fixed issue #99 - no more crashes
```
Would close open issues with number 1 and 99, keywords you can use that will automatically close an issue are
```
close, closes, closed, fix, fixes, fixed, resolve, resolve, resolved
```


<h3> Best-practice commit messages </h3>
The commit messages service at least 3 important purposes
* To speed up the reviewing process
* To help write good release notes
* To help people figure out where and why a change was made in the future

You should structure the commit messages like so, take not to include the blank lines:

Short summary of changes (50 characters max)<br>
<------ Blank line ------><br>
A short explanation if necessary (72 characters max)<br>
<-------Blank line ------><br>
Further paragraphs if needed<br>

<h3>DO</h3>
* Write the summary line and description of what you have done in the imperative mode, that is as if you were commanding someone. Start the line with "Fix", "Add", "Change" instead of "Fixed", "Added", "Changed".
* Always leave the second line blank.
* Line break the commit message (to make the commit message readable without having to scroll horizontally in gitk).

<h3>DON'T</h3>
Don't end the summary line with a period - it's a title and titles don't end with a period.
