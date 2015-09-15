#Google Chrome DevTools

The Chrome DevTools are a set of web authoring and debugging tools built into Google Chrome. They provide web developers deep access into the internals of the browser and their web application. Use the DevTools to efficiently track down layout issues, set JavaScript breakpoints, and get insights for code optimisation.


## Access the DevTools from any web page in Google Chrome:

Select the "View" tab ---> "Developer" ---> "Developer Tools".
Then right-click a page element and choose Inspect element from the context menu.
Keyboard shortcut: Ctrl+Shift+I (or Cmd+Opt+I on Mac).

## Elements panel: inspect DOM and styles;

The Elements panel lets you see everything in one DOM tree, and allows inspection and on-the-fly editing of DOM elements. Use the Elements panel to identify the HTML snippet for some aspect of the page.
For example, view the styles applied to a heading element in the DOM:

To undo changes use Ctrl+Z (or Cmd+Z on Mac) to quickly undo minor changes to the DOM or styles via the Elements panel.	

## Debugging Code Using Chrome Dev Tools
  - allows realtime changes to be seen rather than making adjustments in text editor ---> saving the changes ---> opening the file.
  - more for tweaking than writing full code

## To Start:

In the Dev Tools Window go to the "Elements" tab to begin. Here you can see the DOM tree and are able to cascade & de/recascade through the parent and child elements in the html. Scrolling through the html will highlight the relevant part on the webpage.

## To Edit:

To begin editing double-click an element and enter your changes. These will take effect straight away.
Re: tags, You can edit them but cannot make new ones.
Once you have made your changes you know need to save them.


*If you can't edit code click the magnifying glass in the top left hand corner and then click the element on the webpage you want to inspect/edit.

## To Save:

To save your changes, simply copy and paste from the DevTools window to your file.

## EXAMPLE

I was having problems locating an issue with some HTML & CSS code. In the picture below you can see that there is some CSS styling effecting our (div class = "grid") but our other divs weren't being styled. We didn't know where the problem was. After a bit of searching, I saw that in the DevTools under the "Styles" tab the CSS simply wasn't being applied to the html. This showed that our call to effect the div classes "1" "2" & "3" wasn't working but it was for the "grid".

![dev-tool](https://cloud.githubusercontent.com/assets/12072531/9878154/3eec8076-5bb9-11e5-93ee-1e1361751313.png)
![css-shot](https://cloud.githubusercontent.com/assets/12072531/9878166/465897dc-5bb9-11e5-8b11-462cfc1f7579.png)

I changed the div class names from the digits to their word equivalents which worked! It doesn't look great but we can now change all that!

![color-dev-tool](https://cloud.githubusercontent.com/assets/12072531/9877953/eda69f04-5bb7-11e5-9b27-95a32430f2ac.png)
![color-css-shot](https://cloud.githubusercontent.com/assets/12072531/9878149/3bf77808-5bb9-11e5-95d0-00035dc0e225.png)

## Adv. Dev Tools:
There are many more Dev Tools which can be used within Chrome. This list will be updated with time to hopefully cover 

Debugging with break points:

Chrome DevTools includes powerful breakpoint features that help you find and fix logic errors in your JavaScript code. Use different breakpoint types to control exactly what conditions can trigger a pause in script execution.
