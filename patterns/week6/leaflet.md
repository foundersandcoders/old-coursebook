# Leaflet

This is a _quick_ and _basic_ introduction to the Leaflet map library. Let’s start out by giving you a summary of why you may (or _may not_) want to use Leaflet!

Checkout the splendid repo here for tips and tricks!

https://github.com/hdrdavies/trying-leaflet

#### Pros
* __Open Source__! So almost _anything_ can be customised. Google Maps make you stick to their view of what a map should look like (and you're too much of a creative flower :hibiscus: for that)
* Commercial APIs like Google or Yahoo can change terms at _any time_. So... not great if your app is built on top of it. Leaflet isn’t susceptible to this as Open Source is the best! :+1:
* Very quick to set up and get a map live
* A _well-documented_ API with __loads__ of examples
* Simple source code, _easy_ to use
* Used by Foursquare, Pinterest and Flickr (and Facebook… and Github… and Etsy…)
* Uses new parts of JavaScript, plus HTML5 and CSS3
* Mobile friendly :iphone:
* Free!

#### Cons
* Google being Google are more likely to have quicker loading maps / bugs fixed
* _Some_ people say it has less advanced functionality than the Google API and other open source options but it’s _much_ easier to use

Leaflet has some __excellent__ [tutorials](http://leafletjs.com/examples.html) on their website. A good introductory one can be found [here](http://leafletjs.com/examples/quick-start.html).  

We followed this walkthrough and left the code in a repo [here](https://github.com/hdrdavies/trying-leaflet). We’ve commented throughout the code to show you what each part is doing. Remember to add two script tags to the html file! (we didn’t for a long time) :disappointed:  

The first script tag:

```
<script src="http://cdn.leafletjs.com/leaflet-0.7.5/leaflet.js"></script>
```

Loads the leaflet library :closed_book::green_book::blue_book::orange_book: through its content delivery network (_note the cdn at the start of the URL_). For a short explanation of a CDN please see [here](http://www.webopedia.com/TERM/C/CDN.html)

You will need to signup for a [Mapbox](https://www.mapbox.com/) account, if you would like to add different map templates, or __tile layers__. Tile layers (sometimes referred to as tile overlays) allow you to __superimpose__ images on top of base map tiles. This is an _excellent_ way to add data - such as points of interest or traffic information - and local imagery to your app.  

We added the _renowned_ FAC logo (:heart:) using the tutorial found [here](http://leafletjs.com/examples/custom-icons.html).

When you change the icon of a marker, the ```iconAnchor``` will need to be changed to ensure the icon stays in the same place. (You _may_ notice we haven’t quite managed this).

#### Further Reading

Google vs OpenLayers vs Leaflet: http://robinlovelace.net/software/2014/03/05/webmap-test.html  
More advanced walkthrough:
http://maptimeboston.github.io/leaflet-intro/  
Another take on the best map APIs:
http://www.toptal.com/web/the-roadmap-to-roadmaps-a-survey-of-the-best-online-mapping-tools  
