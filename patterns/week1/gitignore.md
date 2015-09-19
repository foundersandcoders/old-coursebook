## Git Ignore  

A git ignore file allows you to hide files on your local machine from git. This has two inplications:  
* They will be ignored by the git status command, this allows you to commit your project without adding these specific file types
* When pushing to a remote repository on Github, these files will not be pushed

#### Creating and editing a .gitignore file  

##### There are two ways to create a .gitignore file  
* when creating a repository you can select the "Add .gitignore:None" dropdown and select file types you would like to ignore. This file is not viewable in the folder, it will only show up in your text editor when you have linked the project folder to your editor
* You can also create the file via command line using "touch .gitignore"

##### How to edit which files are ignored by .gitignore  
* to ignore a certain file type, used the wildcard preceded by the file name  
e.g. *.css
* This will ignore all CSS file types (not a good idea!)

![Git Ignore PNG ](git_ignore.png?raw=true "Atom Graying out CSS as .gitignore file requests this")

**note** files in .gitignore will still be tracked locally if they are on the repo.
 * to keep the folder on the repo but ignore it locally check this [stackoverflow answer](http://stackoverflow.com/questions/7231608/git-ignore-files-which-are-on-repository)

 * if you do not want the folder on the repo you must delete it on the repo and on everybody's local machines. Then pull down from the repo master and merge
