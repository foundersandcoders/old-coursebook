# Media Queries

Media queries are used to set different styling for different sized screens and devises. They are a key part of responsive design.
Media queries are usually set at the bottom of a style sheet and start with `@media`. then specify a media type, ie `screen` and a size (in either px or ems) ie `300px`.


## Example
Media queries use can use either `max-width` or `min-width`
```CSS
@media screen and (max-width: 300px) {
    /* inside these CSS brackets we can set our styling for screen sizes up to 300px (above 300px this styling will not be applied */
    /* select the classes or id's you wish to style in the normal way */
    body {
            background-color:green ;
      }
    }  
    
} 
```

```CSS
@media screen and (min-width: 301px) {
    /* this media querie styles screens of of sizes 301px up*/
    body {
            background-color:red ;
      }
    }  
    
} 
```

## Media Types
As well as setting style rule for screens of different sizes, you can also target certain media types (see the `screen` part of the queries above.
For example you might wat to target on `print` for printers, or `braille` for braille devices. A full list of media types can be found here: http://www.w3schools.com/cssref/css3_pr_mediaquery.asp

## Orientation
Media queries can also be used to specifiy styles for either landscape or portait views (useful for ipads & phones).
``` CSS
@media tv and (min-width: 700px) and (orientation: landscape) { ...  }
```
## Resolution
Media queries can be used to style screens of different resolutions
```CSS
@media print and (min-resolution: 300dpi) { ... }
```

To look at see the full list of media queries capabilities, check out the mozilla documentation: https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries

## Choosing media queries breakpoints
Devices change alot, and this topic is debated alot. 
Instead of targeting specific devices, many designers & front end devs, now advocate using a mobile-first & content first approach. For info about mobile first, see below. Content first means you consider your content when choosing your breakpoints, for more on this read: http://www.jordesign.com/responsive-breakpoints-from-the-content-out/
And https://responsivedesign.is/articles/why-you-dont-need-device-specific-breakpoints


## Mobile first design
In mobile first design, we think about how our screen will look on mobiles first (yep, it does what it says on the tin), and scale up from there. This helps us keep our code simplier.
This means you code the mobile as default, then add media queries for larger screens, ie `@media screen mim-width 400px`
For more on mobile first checkout: http://www.zell-weekeat.com/how-to-write-mobile-first-css




## Links
http://learnlayout.com/media-queries.html
https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries
http://bradfrost.com/blog/post/7-habits-of-highly-effective-media-queries/




