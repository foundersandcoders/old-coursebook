What is "merging" in Git?

'Merging' describes the act of 'pulling' information from another branch (e.g. the FIXME.md file on the master branch) and combining that information with yours, on your working branch.

How does a merge conflict happen?

It usually occurs when multiple users are active on the same repository, particularly if they are editting the same file. It can also occur if a file has been deleted or a file with the same name has been added.
If the information (e.g. a line on another file) that you pulled from another branch conflicts with the information that you have on your working branch, Git will notify you of 'unmerged paths'. View the message by typing 'git status'.
The details of the conflicting area(s) are highlighted on the file in a text editor.

e.g. Conflict in terminal.

``` shell
$ git status
# On branch contact-form
# You have unmerged paths.
#   (fix conflicts and run "git commit")
#
# Unmerged paths:
#   (use "git add <file>..." to mark resolution)
#
#       both modified:   contact.html
#
no changes added to commit (use "git add" and/or "git commit -a")
```


e.g. Conflict in GUI

![guimergeconflict](https://cloud.githubusercontent.com/assets/11330267/9879741/97398c72-5bc0-11e5-90f8-f7bd9c9f6777.png)

How to fix a conflict

```shell
the number of planets are
<<<<<<< HEAD
nine
=======
eight
>>>>>>> branch-a
```
In the example above:
"nine and "eight" are the conflicting components of the file.
The content between "<<<<<<< HEAD" and "=======" are your changes.
The content between ""=======" and ">>>>>>>" are the changes originating from "branch-a".
"branch-a" is the name of the branch from which the change was pushed.



Manually: Open your version of the file in a text editor. Make the relevant changes. Consult with the user who made the other change if necessary. Once the change has been made, and all parties are satisfied, add and commit your changes. You should now be able to merge the file pulled from Git, with your file.

Application: There are various applications such Kaleidoscope for Apple and kdiff3 for Ubuntu which can make the changes easier to manage. 
