#Fixed Absolute and Relative Positioning

###Static Position
this is the default positioning. 



###Absolute positioning 
Absolute positioning is a bit confusing. Basically the browser will look back up the elements DOM tree for the most recent parent that is positioned anything other than static (ie relative, fixed or absolute).  If an absolutely-positioned element has no positioned ancestors, it uses the document body, and still moves along with page scrolling.

Because absolute positioning is based on the positioning of parent elements, this can make it difficult to workout. You will have to investigate the positioning of an elements parent.



