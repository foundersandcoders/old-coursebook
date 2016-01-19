## CSS positioning :

### Fixed, absolute and relative positioning

 fixed|absolute|relative are the possible values for the property `position` in CSS (as well as static).

###### Fixed

  An element with the position set to `fixed` will be positioned relative to the browser window and will always stay visible on the page even after scrolling on the page.

###### Absolute

  An element with the position set to `absolute` will be positioned either the closest to his parent's position (if the element
  is a child) or relative to the document body. It allow us to move the element anyplace on the page.

###### Relative

  An element with the position set to `relative` will be positioned relative to its normal position. So moving the element (to the
  top, right, bottom or left) will change its position from its normal position.

  ![](http://s15.postimg.org/sthw1ijxn/Screen_Shot_2016_01_19_at_11_42_40_AM.png)

  *Check out more about [the position CSS property](https://developer.mozilla.org/en-US/docs/Web/CSS/position) on MDN.*


### Floats & how to clear floats

###### Floats

  The float property affects all its child elements : if a div is floating on the right, everything that's in that div will be floating on the right as well.

  none|left|right|initial|inherit are the possible values for the property `float` in CSS.

  `none` is the default behaviour of the element
  `left` floats the element to the left and `right` floats the element to the right

  ![](http://s30.postimg.org/xtyel4vnl/Screen_Shot_2016_01_19_at_12_52_32_PM.png)

  `initial` will bring back the default value of the element
  `inherit` the element inherits the float from its parent

###### Clear floats

  The clear property prevents floating element to exceed their container. It indicates that an element is to be placed below the floating elements that precede it.

  `none`	is the default behaviour of the element
  `left`	the element is moved down to free floating elements on the left
  `right`	the element is moved down to free floating elements on the right

  ![](http://s17.postimg.org/u093684mn/Screen_Shot_2016_01_19_at_1_13_59_PM.png)

  `both`	no floating elements allowed on either the left or the right side
  `initial`	sets this property to its default value
  `inherit`	the element inherits the float from its parent

  *Learn more about [float](https://css-tricks.com/all-about-floats/) and [the how and why of clearing floats](https://css-tricks.com/the-how-and-why-of-clearing-floats/) on CSS-Tricks.*


### The system Grids

  Web pages are based on a responsive grid-view of 12 columns. Grids enable you to build solid structure and form into your designs by setting up the layout of the page. Because it uses percentages, your fluid columns will fit into any width.
  It plugs into your existing HTML and CSS. You can either use an already existing system grid from frameworks like Bootstrap and Foundation 5 or create your own one.

![](http://leanderlindahl.se/wp-content/uploads/2011/10/11-1.png)

*Check out more about [What is CSS Grid Layout?](http://gridbyexample.com/what/).*
