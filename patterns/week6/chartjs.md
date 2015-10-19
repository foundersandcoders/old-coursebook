### Chart.js

##### Chart.js is a simple tool that allows you to build charts! Below is an example of a Radar chart that we've made especially for you!

![screen shot 2015-10-19 at 15 01 31](https://cloud.githubusercontent.com/assets/2305591/10579872/7d2e366c-7672-11e5-85fd-dd1a9a433fa7.png)

To view the interactive chart itself please have a look at this [repo](my link)

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



