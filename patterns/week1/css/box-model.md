## The CSS Box Model

"Box Model" used when talking about design and layout and refers to the idea of viewing HTML elements as boxes, which have margin, border and padding properties.

![](https://mdn.mozillademos.org/files/8685/boxmodel-(3)
background colour of the content is extended with the padding (grey). Blue border makes element stand out. Invisible margin allows us greater control with positioning that element.
## See how the box model can affect an HTML element:

### Content

    CSS properties to affect size of the content box:
    width, min-width, max-width, height, min-height, max-height


### Padding Property

Padding extends the background of the content from the content edge until the beginning of the border.

Padding can be set the same to all 4 edges of the content using:


    padding: 10px;

Shorthand for specifying padding for top, right, bottom & left    

    padding:  5px 10px 15px 20px;
    // sets padding: top 5px, right 10px, bottom 15px, left 20px

Shorthand for specifying padding for vertical and horizontal.

    padding: 5px 10px;
    // sets the padding: top and bottom 5px, right and left 10px.


Or we can isolate individual padding to top, right, bottom & left of content edge:

    padding-left: 100px;

[Further Reading - MDN page](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)

### Border Property

The border property refers to a usually slim border that will help the div/image to stand out from its parent. Usually it will be a different colour from the background of the padding/content and the parent.

    border: 3px solid grey;
    //sets a solid grey border of 3px around all 4 edges.

For alternative border properties shorthand, see the padding property section above but replace 'padding' with 'border'.

[Further Reading - MDN page](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

### Margin Property

Margin is an invisible box which is used to separate divs/images from each other.



[Further Reading - MDN page](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)

### Further - what are the possible units given (px, %, em)



#### Browser Compatibility:
Note: Internet Explorer 8 and earlier versions include padding and border properties in the width property.  To prevent this add the following to the top of your HTML page.
 ```html
<!DOCTYPE html>
```

### Further Reading:
