## @media : CSS Media queries

## What
In one line: Media queries allow us to change how a page looks when the user changes things like the size of the screen.


## Why
Responsive web design refers to websites that respond to things like the size of the screen the user is using.  

For example on a desktop computer, it might be helpful to have a large menu bar with multiple headings, but when viewing that same website on an ipad or smartphone, the large menu will be difficult to see and use. We may want our website to respond to this change in screen size to a more suitable drop-down menu. Media queries, a feature of CSS3, will allow these changes to take place automatically and can be 'triggered' by changing screen-size, resolution, width, height, resolution and orientation changes.

![](http://artisantalent.com/wp-content/uploads/2015/04/embrace-responsive-web-design-1024x614.jpg)
Slight alteration in the style of the header between the laptop, tablet and smartphone.

## How
Media queries will determine when certain certain CSS styles should be applied.  



##### General structure:
A media query contains a media type and will test one or more media features (which make up expressions) that can resolve to true or false.

In the below example, the **media type is the screen or print** and the **expressions are given in brackets** will be true or false depending on screen size.  The **only** keyword will hide the style from old browsers that do not support.

```CSS3
/* default case */
body {
  background-color: black;
}

/* for screen widths 200px to 499px */
@media only screen and (max-width: 499px) and (min-width: 200px) {
    body {
        background-color: blue;
    }
}

/* for screen widths above 500px */
@media only screen and (min-width: 500px) {
    body {
        background-color: yellow;
    }
}

/* when printed we do not want a background colour to save on precious ink */
@media print {
    body {
        background-color: white;
    }
}
```
Have a play around with an @media screen query following [this link](http://www.w3schools.com/css/tryit.asp?filename=tryresponsive_mediaquery)


## Loading an entirely different stylesheet
Add the following html link element to your html file to load an entirely different stylesheet depending on screen size:
```html
<link rel="stylesheet" media="screen and (min-device-width: 1000px)" href="1000.css" />
```


## What else can they be used for?
As mentioned earlier, media queries can be used to recognise a range of **media types** and **media features** we can use to create expressions. [See this link](http://www.w3schools.com/cssref/css3_pr_mediaquery.asp).

## Browser support
Media queries are supported by all modern browsers and mobile browsers including IE9 :)
**Older browsers may not support your media queries** so remember to use *only* keyword where appropriate.

#### Fun Fact
@media was introduced in CSS2 in the form of 'media types' (type of device) but received no love and lacked support from devices. Media queries came out with CSS3 which are more adaptable.

### Further reading
[CSS Tricks 1](https://css-tricks.com/resolution-specific-stylesheets/)

[CSS Tricks 2](https://css-tricks.com/css-media-queries/)
