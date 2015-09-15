The Chrome DevTools are a set of web authoring and debugging tools built into Google Chrome. They provide web developers deep access into the internals of the browser and their web application. Use the DevTools to efficiently track down layout issues, set JavaScript breakpoints, and get insights for code optimisation.


Access the DevTools from any web page in Google Chrome:

Select the Chrome menu and choose More tools > Developer tools.
Right-click a page element and choose Inspect element from the context menu.
Keyboard shortcut: Ctrl+Shift+I (or Cmd+Opt+I on Mac).

Elements panel: inspect DOM and styles;

The Elements panel lets you see everything in one DOM tree, and allows inspection and on-the-fly editing of DOM elements. Use the Elements panel to identify the HTML snippet for some aspect of the page.
For example, view the styles applied to a heading element in the DOM:

insert pic??

To undo changes use Ctrl+Z (or Cmd+Z on Mac) to quickly undo minor changes to the DOM or styles via the Elements panel.	

debugging with break points;

Chrome DevTools includes powerful breakpoint features that help you find and fix logic errors in your JavaScript code. Use different breakpoint types to control exactly what conditions can trigger a pause in script execution.

Debugging Code Using Chrome Dev Tools
  - allows realtime changes to be seen rather than making adjustments in text editor ---> saving the changes ---> opening the file.
  - more for tweaking than writing full code

To Start:
In the Dev Tools Window go to the "Elements" tab to begin. Here you can see the DOM tree and are able to cascade & de/recascade through the parent and child elements in the html. Scrolling through the html will highlight the relevant part on the webpage.

To Edit:
To begin editing double-click an element and enter your changes. These will take effect straight away.
Re: tags, You can edit them but cannot make new ones.
Once you have made your changes you know need to save them.


*If you can't edit code click the magnifying glass in the top left hand corner and then click the element on the webpage you want to inspect/edit.

To Save:
To save your changes, simply copy and paste from the DevTools window to your file.

EXAMPLE

I was having problems locating an issue with some HTML & CSS code. In the picture below you can see that there is some CSS styling effecting our (div class = "grid") but our other divs weren't being styled. We didn't know where the problem was. After a bit of searching, I saw that in the DevTools under the "Styles" tab the CSS simply wasn't being applied to the html. This showed that our call to effect the div classes "1" "2" & "3" wasn't working but it was for the "grid".

![css-shot](https://cloud.githubusercontent.com/assets/12072531/9877968/00a2f3b4-5bb8-11e5-8446-2bbc3f7d5377.png)

I changed the div class names from the digits to their word equivalents which worked! It doesn't look great but we can now change all that!

![color-dev-tool](https://cloud.githubusercontent.com/assets/12072531/9877953/eda69f04-5bb7-11e5-9b27-95a32430f2ac.png)
![color-css-shot](https://cloud.githubusercontent.com/assets/12072531/9878019/55d0fe08-5bb8-11e5-87de-1f408fa9f860.png)

