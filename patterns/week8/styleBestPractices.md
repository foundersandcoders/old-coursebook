# **REACT** - Styling Best Practices

>What we refer to as "style" actually includes quite a few concepts:  
Layout — how an element/component looks in relationship to others  
Appearance — the characteristics of an element/component  
Behavior and state — how an element/component looks in a given state



### Inline Styling

Those of you who are new to REACT.js are probably used to styling your web apps  
 using a separate CSS stylesheet. This tutorial will walk you through the process of  
how to write your CSS inline (within your REACT code) and then apply it within the  
properties of your desired HTML element.

You can find more information about inline styling **_[here](http://facebook.github.io/react/tips/inline-styles.html)_**.


#### Step 1

Construct a simple object with any CSS properties of your choice as keys, and their  
attributes as values. For example:

```javascript
var elementStyle = {
  color: red,
  background-color: blue
}
```  

#### Step 2

Add the name of the object into the properties of the element that you wish to style.  
It takes a property name of _'style'_ and is implemented with curly braces like so:


```javascript
<div style={elementStyle}></div>
```

You can also download npm modules that can help you with your inline styling such  
as 'Radium', 'React Style' or 'React Inline'.

### Modularizing CSS with REACT

It's possible to combine many style objects and access them individually using dot  
notation. Continuing from the first example, imagine we have another div that we want  
to style but we don't want to interfere with our existing div styling. We can create a  
variable that holds each of these styles in the form of objects:

```javascript
class MyNotification extends React.CSSComponent {
  render() {
    var styleMap = this.mountStyles`
      @media (min-width: 600px) {
        .notification {
          font-family: Sans-Serif;
        }
      }
      .notification {
        color: blue;
      }
      .notification-hint {
        color: red;
      }`;
    return (
      <div className={styleMap.notification}>
        {this.props.prompt}
        <span className={styleMap.notification-hint}>
          {this.props.hint}
        </span>
      </div>);
  }
}
```

### Styling with Separate CSS Files for each Component

Another way to style your app is to use separate CSS files for each of your components. Here's an example file structure that uses this method:

![SCREENSHOT](https://cloud.githubusercontent.com/assets/12450298/10915361/5f872a3c-824e-11e5-8f7f-2a7db70eee07.png)

They have to be required into the CSS ```main.js``` individually in the following format:

```javascript
'use strict';

require('./components/App.css');
require('./components/Header.css');
require('./components/List.css');
require('./components/Footer.css');
```
