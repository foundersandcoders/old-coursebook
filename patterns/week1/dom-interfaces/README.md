# DOM interfaces

What are DOM interfaces and how do they inherit from each other?

The Document Object Model (DOM) is a programming interface for interacting with HTML documents (SVG and XML too) - it lets YOU as a JavaScript programmer interact with and change different parts of the document.

- *although the DOM can be altered using other languages, JavaScript is the most common*

![this is the dom](https://upload.wikimedia.org/wikipedia/commons/5/5a/DOM-model.svg)

The key idea of the DOM is:

### Every node is a particular type of Object.

In the DOM, all HTML elements are defined as objects! This is great, it means we can easily access these elements via JavaScript

### So what on earth is a DOM interface then?!

![confused](https://myenglishexpressions.files.wordpress.com/2015/02/confused-face.jpg)

Very simply **DOM Interfaces** are the properties and methods given to each **type** of element

each node in the tree *(above the confused person)* - like element, document, text is a specific type of **DOM interface**

Some of the most commonly used DOM interfaces include:

* `Window`
* `Document`
* `Element`
* `Node`
* `Text`

###### You can see LOADS of these if you type `window` into the js console in your browser

### DOM interface Properties

A property is a value you can get or set (like changing the content of an HTML element). eg:

````HTML
<p id='fac-rocks'>Hello FAC7!</p>
````

the 'Hello FAC7!' part is the innerHTML property of the p element

### DOM interface Methods

````javascript
document.getElementById('fac-rocks')
````

'getElementById' is a method available to the **document interface**

### Heirarchy

The DOM interface has a Heirarchy where different interfaces **inherit** properties and methods from their parents

For example: `Element` inherits from the more generic `Node`. These two interfaces provide many of the methods and properties you use on individual elements. These elements may also have specific interfaces for dealing with the kind of data those elements hold.

### It's All an Abstraction

It is important to realize that these interfaces are an abstraction, they are a means of specifying a way to access and manipulate an application's internal representation of a document

![abstraction](https://s-media-cache-ak0.pinimg.com/736x/29/f4/cf/29f4cf6670d00a6e022bf5aabfc36814.jpg)

##### An abstraction of the DOM?


## Further Reading

Brilliant Mozilla documentation on the DOM: [https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

A list of DOM interfaces: [https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
