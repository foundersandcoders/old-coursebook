# GoogleMapsAPI
Tutorial for using google maps API

## How to set up Google Maps API
 1. Load the google API using ```<script src="http://maps.googleapis.com/maps/api/js"></script>```
 2. If you plan for heavy traffic, get your API key from https://console.developers.google.com and add the script tag ```<script src="http://maps.googleapis.com/maps/api/js?key=YOUR_KEY"></script>```
 3. Set map properties by creating a function to initialize the map. Within this function you set up your map object with properties center, zoom and mapTypeId.
 4. Create a new map. You can create as many map objets as you wish. 
 
    ```javascript
    function initialize() {
        var mapProp = {
          center: new google.maps.LatLng(51.508742, -0.120850),
          zoom: 7,
          mapTypeId: google.maps.MapTypeId.ROADMAP
        };
        map = new google.maps.Map(document.getElementById("googleMap"), mapProp);
      }
    ```
 5. Add event Listener to load your map.

    ```javascript
    google.maps.event.addDomListener(window, 'load', initialize)
    ```
    
 6. Create basic HTML where your map will go.

    ```HTML
    <div id="googleMap" style="width:500px;height:380px;"></div>
    ```


## Google Map Overlays
There are many different overlays you can use e.g.
  - Marker - Single locations on a map. Markers can also display custom icon images
  - Polyline - Series of straight lines on a map
  - Polygon - Series of straight lines on a map, and the shape is "closed"
  - Circle and Rectangle
  - Info Windows - Displays content within a popup balloon on top of a map
We have chosen two of the most useful.

### Markers
To add a new marker:

1. Create a marker object with the position value. Call ```marker.setMap(map)```

 ```javascript
 var marker=new google.maps.Marker({
   position:new google.maps.LatLng(51.508742,-0.120850),
   });
 marker.setMap(map);
 ```

2. You can also add animations to your markers by adding it into your marker object e.g. ```animation: google.maps.Animation.BOUNCE```

### Info Windows
1. create an infowindow object:

 ```javascript
 var infowindow = new google.maps.InfoWindow({
     content:"Hello World!"
   });
 ```
 
2. For this to appear when you click, add the following below:

 ```javascript
 marker.addListener('click', function(){
     infowindow.open(map, marker)
   })
 ```
 
3. Note the infowindow is specific to a previously defined marker and map.

### Allowing users to create markers
1. Create a listener for the entire map which then runs a function.

 ```javascript
 map.addListener('click', function(event){
     placeMarker(event.latLng);
 })
 ```
 
2. Create the placeMarker function.

 ```javascript
 function placeMarker(location) {
   var marker = new google.maps.Marker({
     position: location,
     map: map,
   });
   var infowindow = new google.maps.InfoWindow({
     content: 'Latitude: ' + location.lat() +
     '<br>Longitude: ' + location.lng()
   });
   infowindow.open(map,marker);
 }
 ```

## Our Tutorial
We have created a quick example of how you can use the Google Maps API. The functionalities include:
  - search
  - create marker from search value
  - zoom on the searched marker

Clone our [repo](https://github.com/Conorc1000/GoogleMapsAPI) to follow along.

To see the basic HTML outline go to start.html. finished.html shows a working example where you can type in an address, the map then zooms to that address and sets a marker. 

Use start.html as a starting point to make your own google map functions.

Here are the steps we took to create our finished.html file.
1. We first created the initialize function which put a map onto the page when it loads.
2. We then created the findAddress function which is sending a request to the Google Maps API.
3. When the response is sent back from the API we go through the JSON object to access the longitude and latitude coordinates.
4. The function createMarker is then run with these coordinates to make the marker and zoom to it.

## References
http://www.w3schools.com/googleapi/default.asp

https://developers.google.com/maps/documentation/javascript/
