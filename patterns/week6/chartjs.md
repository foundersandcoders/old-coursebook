### Chart.js

##### Chart.js is a simple tool that allows you to build charts! Below is an example of a Radar chart that we've made especially for you!

![screen shot 2015-10-19 at 15 01 31](https://cloud.githubusercontent.com/assets/2305591/10579872/7d2e366c-7672-11e5-85fd-dd1a9a433fa7.png)

To view the interactive chart itself please have a look at this [repo](https://github.com/FAC6/book/blob/master/patterns/week6/chartjs.html)

Chart.js requires HTML5 canvas elements, it is responsive, modular, interactive and most importantly its OPEN SOURCE!

You can create six chart types using chart.js and we thouroughly recommend going through their [documentation](http://www.chartjs.org/docs) as it is very simple and well documented.

### How to create your own Radar Chart

 - create an index.html file and paste the following template
 ```html
 <!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Radar Chart</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/1.0.2/Chart.min.js"></script>

  </head>
  <body>
    <h2 style="text-align:center;color:white;">Github Compare</h2>
    <div class="" >
      <canvas id="myChart" width="800" height="400"></canvas>
    </div>

  </body>
</html>
 ```
 The CDN script loads the chart.js library (its tiny at 11.01KB). The canvas element is a HTML5 feature use to render graphics in your browser, read more [here](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)
 - Add the following data into your main script file (can be done inline for the tutorial)
 ```javascript
 var data = {
      labels: ["Followers", "Following", "Starred", "Total Commits", "Longest Streak"],
      datasets: [{
        label: "Eoin",
        fillColor: "rgba(255, 0, 0, 0.2)",
        strokeColor: "rgba(255, 0, 0, 1)",
        pointColor: "rgba(255, 0, 0, 1)",
        pointStrokeColor: "#fff",
        pointHighlightFill: "#fff",
        pointHighlightStroke: "rgba(220,220,220,1)",
        data: [23, 28, 9, 38.5, 19]
      }, {
        label: "Sohil",
        fillColor: "rgba(16, 200, 0, 0.2)",
        strokeColor: "rgba(0, 191, 31, 1)",
        pointColor: "rgba(16, 196, 0, 1)",
        pointStrokeColor: "#fff",
        pointHighlightFill: "#fff",
        pointHighlightStroke: "rgba(151,187,205,1)",
        data: [16, 19, 19, 30.2, 12]
      }, {
        label: "Kata",
        fillColor: "rgba(0, 170, 255, 0.2)",
        strokeColor: "rgba(0, 170, 255, 1)",
        pointColor: "rgba(9, 173, 255, 1)",
        pointStrokeColor: "#fff",
        pointHighlightFill: "#fff",
        pointHighlightStroke: "rgba(151,187,205,1)",
        data: [22, 24, 27, 26.5, 12]
      }, {
        label: "Rachel",
        fillColor: "rgba(246, 111, 0, 0.2)",
        strokeColor: "rgba(251, 181, 0, 1)",
        pointColor: "rgba(255, 184, 0, 1)",
        pointStrokeColor: "#fff",
        pointHighlightFill: "#fff",
        pointHighlightStroke: "rgba(151,187,205,1)",
        data: [25, 37, 31, 26.5, 11]
      }]
    };

 ```
 At this point have another look at the (Radar chart.js documentation)[http://www.chartjs.org/docs/#radar-chart]
 - Get the context object from your canvas using the following script, this is the object that provides us the tools required 2d rendering, in this case it is `chart` which uses the context:  
 ```javascript
 var ctx = document.getElementById('myChart').getContext("2d");  
 ```
 - Next create a chart object giving it a reference to the context object:
 ```javascript
 var myChart = new Chart(ctx);
 ```
 - Finally create the chart using your own custom options and your dataset (in our case the dataset is provided above):
 ``` javascript
 myChart.Radar(data, options);
 ```
 - The options parameter allows users to customise the look and feel of the charts, we have provided an example of the option object which changes certain styles of the chart. To view all the options available please view the [following](http://www.chartjs.org/docs/#radar-chart-chart-options)
```javascript
     var options = {
      pointLabelFontColor: "#ffffff",
      responsive: true,
      animationSteps: 200,
      animationEasing:"easeOutExpo",
      pointLabelFontSize: 18  ,
      scaleLineColor: "#ffffff",
      scaleLineWidth: 1,
      maintainAspectRatio: false,
      legendTemplate: "<ul class=\"<%=name.toLowerCase()%>-legend\"><% for (var i=0; i<datasets.length; i++){%><li><span style=\"background-color:<%=datasets[i].strokeColor%>\"></span><%if(datasets[i].label){%><%=datasets[i].label%><%}%></li><%}%></ul>",
    }
```
- You are now done, if you view the html in the browser you will view a Radar chart very similar to ours. Well Done!

##### Summary
### Pro
- Very Simple to use
- Good Documetation
- Open Source
- Lots of customisation
### Cons
- Not SVG based
- No Inbuild Legend
- only 6 chart types



Links:
- http://www.chartjs.org/
- http://www.chartjs.org/docs/


