# DOM manipulation

### Types of DOMs
There are a few different types of the DOM including the Core DOM, XML DOM and the HTML DOM. The latter is the one that we will be focusing one.

### JavaScript and HTML
JavaScript is the programming language of HTML and the Web so will be essential when trying to manipulate the HTML DOM. JS can be used to change all HTML elements, HTML attributes and CSS styles in a page. It can be used to add new or remove existing HTML elements and attributes; and can also react to all existing HTML events in the page or create new ones.

An example of changing an HTML element in the DOM would be changing a `<p>` element to say something other than what was originally written in it.

The following text would have said hello in Japanese but as that would probably not be the most appropriate language to use here we have used JavaScript to change it to English.

````html
<!DOCTYPE html>
<html>
<body>

<p id="p1"> Konnichiwa FAC7!</p>
````
````javascript
<script>
document.getElementById("p1").innerHTML = "Hi FAC7!";
</script>


</body>
</html>
````

HTML 4 added the ability to let events trigger actions in the browser, like starting a JavaScript when a user clicks on an element.

### Ways of manipulating the HTML DOM
You often want to manipulate HTML elements and to do so you first need to find the elements. There are multiple ways of going about this.

* By id
* By tag name
* By class name
* By CSS selectors
* By HTML object collections


The most simple way to find an HTML element in the DOM is by using element id.

````
var test = document. getElementById("elementName");
````

If the element is found it will return the element as an object in test otherwise it will contain null.

The following example will find all the `<h1>` elements

````
var test = document.getElementsByTagName(“h1”);
````

To find elements buy class name you would use

````
var x = document.getElementsByClassName(“className”)
````

This will return all elements with the class name className.

To find all HTML elements that match a specific CSS selector (id, class, type, etc) you will need the querySelectorAll() method


The final (and probably the most difficult) is finding HTML elements by HTML objects. See further reading for more information on this.



### Further reading

The following links will allow you to get hands on experience testing various ways of changing HTML elements using JavaScript and how to access HTML elements in a HTML page.
http://www.w3schools.com/js/js_htmldom_html.asp
http://www.w3schools.com/js/js_htmldom_elements.asp
