## Responsive font & div sizing

### Responsive Font

Making your `font-size` respond to viewport or container size should be a must to complete your responsive designs. Having a fixed `font-size` across devices is not always a good idea.

The key point is to get a readable font size and a comfortable line length in most viewports. CSS viewport units and media queries provide the means to implement a responsive font size.


![responsive](https://cdn.css-tricks.com/wp-content/uploads/2014/05/vw.gif)

### Viewport

The Viewport is the browser window size. If the viewport is 40cm wide, 1vw == 0.4cm.

For use with font-size, I guess it's one "letter" that takes on that size, but as we know, in non-mono-spaced fonts the width of a letter is rather arbitrary. I find you just need to tweak around with the values to get it how you want it.

- 1vw = 1% of viewport width

- 1vh = 1% of viewport height

- 1vmin = 1vw or 1vh, whichever is smaller

- 1vmax = 1vw or 1vh, whichever is larger


| CSS Viewport Units
|---------------------------------------------------------
| `vw` Relative to 1% of the width of the viewport*
| `vh` Relative to 1% of the height of the viewport*
| `vmin` Relative to 1% of viewport's* smaller dimension
| `vmax` Relative to 1% of viewport's* larger dimension

### Some examples

```css
h1 {
  font-size: 5.9vw;
}

h2 {
  font-size: 3.0vh;
}

p {
  font-size: 2vmin;
}
```

***

### div sizing
The `<div>` html tag is used to group block-elements to format them with CSS.

### Example

```css
div {
    box-sizing: border-box;
    width: 50%;
    float: left;
}
```
This code specify two bordered boxes side by side. If you want to see the demo click here.


***

### Further reading

[Viewport sized typography](https://css-tricks.com/viewport-sized-typography/)

[Responsive font size css](http://codeitdown.com/responsive-font-size-css/)

[HTML div tag](http://www.w3schools.com/tags/tag_div.asp)

[CSS3 box-sizing property](http://www.w3schools.com/cssref/css3_pr_box-sizing.asp)
