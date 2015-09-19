## Responsive Font Size

#### Three ways to create responsive font  
* Using viewport units you can set your font size as a percentage of the browser size. The following units are available:  
 * `vw` - sets the font size to be a percentage of the browser width
 * `vh` - sets the font size to be a percentage of the browser height
 * `vmin` - the shortest of the above two dimensions
 * `vmax` - the longest of the above two dimensions


* Using media queries you can set discrete font sizes for various viewport sizes
 * Use `@media (min-width:2000px) { your CSS }`. will apply the CSS only when the screen width is greater than `2000px`.
 * Use `@media (max-width:1000px) { your CSS }`. will apply the CSS only when the screen width is less than `1000px`.


* Use `em` and `rem` units to access pixel sizes of preset fonts.
 * `font-size=2em` this means that the font size of the text will be set to twice that of the default. e.g. you may set the font size of a paragraph to be `3em`. if the default font size is `12px` then the paragraph font size in pixel will be `36px`
 * `rem` is similar to `em`, except it look for at the font size of the html element. This allows all responsive font to look at the same root font size.

 #####For more information on responsive font sizing visit: http://codeitdown.com/responsive-font-size-css/

## Responsive Div Size

#### Three ways to create responsive Divs  
* Divs width can be set as a percentage of the parent width. e.g. `<div style="width:100%">` will set the width of the `div` to the width of its parent.
* As above media queries can all be used to customise the size of `div` elements
* As above the units `em` & `rem` can be used in setting the size of `div` elements


###Final Thoughts

##### Although all these techniques can be effective on their own, they work best when used in conjunction with each other
