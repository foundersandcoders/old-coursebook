***Setting up file structure (with HTML/CSS/JS organised in folders as opposed to sitting in root***

The importance of organisation and accuracy in managing your files and folders will hold you in good stead as the size and number of projects increases. The need for having a well organised and structured system for your files will prevent you from making various errors when referencing file paths and looking for files relevant to the current project your working on. There are some generic file names such as ```index.html, stylesheet.css, custom.css, app.js amongst others but it is imperative that these are stored in the relevant directory and not on the root file as you could easily have the same file name for two different projects creating confusion.

**What is a Root Folder?***

The root folder, also called the root directory, of any partition is the "highest" folder in the hierarchy.
The root directory of a drive, contains all other folders and can ofcourse also contain files.
For example, the root directory of the main partition on your computer is probably C:\. The root folder of your DVD or CD drive might be D:\. Luckily in Ubuntu you don't have access to your root folder unless you RESET Root Password.

***How to Structure - One Size Doesn't Fit All***

The depth of your folder hierarchy and the number of individual files should make sense for the size of the website. Keep it in perspective.Here’s a quick list for the files that compile to form a typical website, and how you might structure things accordingly. It's best practice to create a directory named "web-projects" or something similar where you can have subfolders named after each project you're working on. 

```
e.g. structure of a Portfolio-site


Web-Projects/
				Portfolio-site/
				                images/
					            		profile.jpg
					            		background.jpg
					            css/
					            		main.css
					            		normalise.css
					            		grid-sheet.css

					            javascript/
						           	   app.js
					            		   jquery.js
					            assets/
					            		videos/
			                			pdfs/
								
								README.txt
								index.html	    						
								       

e.g. Example of a larger site with multiple pages for a Restaurant "Big Burger"				  

Big-Burger/
	  website/
            images/
                boxes/ /* often still necessary for IE... */
                    red-bottom-left.png
                    red-bottom-right.png
                    red-top-left.png
                    red-top-right.png
                navigation/
                    navigation-sprite.png
                    background.png
                logo.png
                page-background.png
                twirly-list-dot.png
            css/
                layout.css
                content.css
                print.css
                mobile.css
            javascript/
                jquery.js
                datepicker.js
                site.js
            assets/
                pictures/
                videos/
                pdfs/
            templates/
                blog/
                emails-plaintext/
                emails-html/
                social/
                mobile/
                *.tpl
            content/
        code/
            *.php
        reports/
        graphics/
```

...That might look a bit complicated without the context. Here's a suggestion for a basic structure that will help to organise the different component files.

- Create a folder for the website project:

	```
	- fac_proj_1				// Make sure this folder name (and all other filenames) will be 							coherent to anyone and everyone! 
		- index.html			// This file creates the main point of entry. 
	```

- The website will genereally be comprise of HTML, CSS, Javascript and Image files. Some of these will be specific to 'fac-proj-1', others might be shared with other projects. It's important to make a distinction here. Let's do this by grouping the files into general-purpose (used in multiple projects) and project-specific folders.

	```
	- fac_proj_1
	  	- general			// include all the general purpose files and libraries in here.
	  	- resources			// include all the files that will be editted in this folder.
		- index.html			
	```

- Next, making folders to include files that correspond to either HTML, CSS, Javascript or Images is recommended.

	```
	- fac_proj_1
	  	- general			// include all the general purpose files and libraries in here.
			- some_css_library
			- some_jquery_library		  	
		- resources			// include all the files that will be editted in this folder.
			- html
				- index.html
			- css
				- blue_theme
					- blue_background.png
				- blue_theme.css				
				- index.css
			- js
				- index.js		
		- index.html			
	```

(adapted from http://stackoverflow.com/questions/24199004/best-practice-to-organize-javascript-library-css-folder-structure see this link for more info on this style of structuring!)

***Why is it better to have HTML, CSS & JS in separate files?***

If you're working on a project with a number of people, each working on different parts (HTML/CSS/JS) of the project, it makes sense to edit just the part of code that is relevant to your role. It can therefore be better, safer and more efficient to separate the project into different sections accordingly, and some of the main benefits of doing this are outlined below.

1) Efficiency - If the code for the project is contained in one large file, everyone who needs to work on the code will need to download and work on this massive file. That not only means longer download times, but also makes the possibilities of merge conflicts occurring higher...

2) (Accidental) Merge Conflicts! (See above).

3) Maintenance - you only need to make updates in a specific file if, for example, you want to change something in HTML. Finding specific objects easier. Pushing to the remote (Github) branch becomes faster. Also when you commit that change, you can go back in Github and find exactly when you changed something and how, just by considering the file in which the change was made (the comments we put when we push ( -m "comment" ) probably helps too). 

4) Good practise and a clean structure - HTML should only be used to structure content, CSS should be used to style the webpage and Javascript should be used for the functionality of the website. If your/your team's code ever gets passed on to another team, it will be easier for them to understand and follow on with a coherent and separate filing structure.

***It's good to know that there are conventions, but there are different styles, and no wrong one (unless it's really messy)!***
