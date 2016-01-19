# Git on the Command Line: *Command Cheatsheet*

## Why use the Command Line?
* It's faster.
* More control over branching and merging.
* Many developers use it consistently so help from stack overflow will generally come in Git Command Line form.

## Before get started...
1. Install git on your computer.
  * The version you install will depend on your operating system (see [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for further details).
2. Assert your identity.
  * Open the Terminal and set up your user name and email address:
  ![](http://buzzinmediagroup.com/wp-content/uploads/2015/03/david_hasselhoff_artist_aria_210812_640x360-david-hasselhoff-joins-sharknado-3.jpeg)
  ```
  $ git config --global user.name "David Hasselhoff"
  $ git config --global user.email callmedaveybaby@thehoff.com
  ```
3. Check your settings.
  * Worth doing to make sure everything's as it should be.
  * Open the Terminal and type:
  ``
  $ git config --list
  ``
  * You should see all the settings Git can find at that moment.

## If you ever need help...
* Git comes with its own manual page.
* You can access this (even offline!) using one of the following three commands:
````
$ git help //(+ whatever you need help with e.g. 'config')
$ git config --help
$ man git-config
````

## Ready to go?
* Use [this cheatsheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf) to get cracking!

## References
* [Downloadable cheatsheet](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)
* [First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
* [Github for Beginners: Don't get Scared, get Started](http://readwrite.com/2013/09/30/understanding-github-a-journey-for-beginners-part-1)
* [Git: Moving from GUI to Command Line](http://aaronmbushnell.com/git-moving-from-gui-to-command-line/)
* [In the Beginning was
the Command Line](http://www.cryptonomicon.com/beginning.html)
