#Fixed Absolute and Relative Positioning

###Static Position
this is the default positioning. 

###Relative positioning

Essentially means "relative to itself". If you specify position:relative then you can use top or bottom, and left or right to move the element relative to where it would normally occur in the document. However, if you set position: relative; on an element but no other positioning attributes (top, left, bottom or right), it will have no effect on it's positioning.

E.g. If you specify position:relative and give the element some other positioning attribute, such as, top: 10px; it will shift it's position 10 pixels down from where it would normally be.

![an example of relative positioning] (http://blog.teamtreehouse.com/wp-content/uploads/2012/11/position-relative.jpg)


###Absolute positioning 
Absolute positioning is a bit confusing. Basically the browser will look back up the elements DOM tree for the most recent parent that is positioned anything other than static (ie relative, fixed or absolute).  If an absolutely-positioned element has no positioned ancestors, it uses the document body, and still moves along with page scrolling. **Absolute positioning, positions elements relative to its nearest non static parent**.

Because absolute positioning is based on the positioning of parent elements, this can make it difficult to workout. You will have to investigate the positioning of an elements parent.

###Fixed positioning
Elements are fixed in a static position to the viewport (ie the window you can see on the browser).




### Useful links
http://learnlayout.com/position.html


