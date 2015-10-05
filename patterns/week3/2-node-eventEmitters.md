#Event Emitters 
Many objects in Node.js emit events: a net.Server emits an event each time a peer connects to it, a fs.readStream emits an event when the file is opened. All objects which emit events are instances of events.EventEmitter. You can access this module by doing: require("events");

So, what exactly does the EventEmitter class do? Put simply, it allows you to listen for "events" and assign actions to run when those events occur. If you're familiar with front-end JavaScript, you'll know about mouse and keyboard events that occur on certain user interactions. These are very similar, except that we can emit events on our own, when we want to, and not necessary based on user interaction. 

An important question is this: why would you use the event model? In Node, it's an alternative to deeply nested callbacks. A lot of Node methods are run asynchronously, which means that to run code after the method has finished, you need to pass a callback method to the function.
Eventually, your code will look like a giant funnel, for detailed examples of the problems involved with deeply nested callback functions see [callbackhell](http://callbackhell.com/). To prevent this, many node classes emit events that you can listen for. This allows you to organize your code the way you'd like to, and not use callbacks.

We've provided an example below which shows two of the most commonly used event emitter events, .on and .emitt . Think of these as working together to replace nested callback functions. 
<h2>Using <code>EventEmitter</code>
</h2>
<p>We'll begin with the <code>EventEmitter</code> class on its own. It's pretty simple to get at: we just require the events module:</p>
<pre class="brush: js noskimlinks noskimwords">
    var events = require("events");</pre>
<p>This <code>events</code> object has a single property, which is the <code>EventEmitter</code> class itself. So, let's make a simple example for starters:</p>
<pre class="brush: js noskimlinks noskimwords">
    var EventEmitter = require("events").EventEmitter;

    var ee = new EventEmitter();
    ee.on("someEvent", function () {
        console.log("event has occured");
    });

    ee.emit("someEvent");</pre>
<p>We begin by creating a new <code>EventEmitter</code> object. This object has two main methods that we use for events: <code>on</code> and <code>emit</code>. </p>
<p>We begin with <code>on</code>. This method takes two parameters: we start with the name of the event we're listening for: in this case, that's <code>"someEvent"</code>. But of course, it could be anything, and you'll usually choose something better. The second parameter is the function that will be called when the event occurs. That's all that is required for setting up an event. </p>
<p>Now, to fire the event, you pass the event name to the <code>EventEmitter</code> instance's <code>emit</code> method. That's the last line of the code above. If you run that code, you'll see that we get the text printed out to the console.</p>
<p>That's the most basic use of an <code>EventEmitter</code>. You can also include data when firing events: </p>
<pre class="brush: js noskimlinks noskimwords">
    ee.emit("new-user", userObj);</pre>
<p>That's only one data parameter, but you can include as many as you want. To use them in your event handler function, just take them as parameters:</p>
<pre class="brush: js noskimlinks noskimwords">

    ee.on("new-user", function (data) {
        // use data here
    });</pre>
    
  As you can see, the .on method is very much like declaring a callback function and the .emitt method is much like the call to that callback function when it is actually used. Below is a more detailed example to show you how these two methods work together to avoid deeply nested callback functions.
```JavaScript    
    var EventEmitter = require('events').EventEmitter;
var emitter = new EventEmitter();
var fs = require('fs');

emitter.on('start_read',function(file_name){
      console.log("Started Reading file....\n\n");
      fs.readFile(file_name, 'utf8', function (err,data) {
        if (err) {
          emitter.emit('error','from_read');
        }
        else{
            console.log("Done Reading file....\n\n");
            emitter.emit('print_content',data);
          }
  });

});

emitter.on('print_content',function(data){
      console.log("Printing content of file....\n\n");
      console.log(data);
      emitter.emit('done');

});

emitter.on('error',function(type){

      console.log("Faced error while "+type);
      emitter.emit('done');

});

emitter.on('done',function(){

      console.log("Ok its done !");

});
emitter.emit('start_read','/etc/hosts')
```
Another useful eventemitter method is <code>once</code>. It's just like the <code>on</code> method, except that it only works once. After being called for the first time, the listener is removed.</p>

    ee.once("firstConnection", function () { console.log("You'll never see this again"); });
    ee.emit("firstConnection");
    ee.emit("firstConnection");
<p>If you run this, you'll only see the message once. The second emission of the event isn't picked up by any listeners (and that's okay, by the way), because the <code>once</code> listener was removed after being used once. </p>

###Recommended reading:
* This is a must read, providing most of the content here but goes into more methods towards the end: http://code.tutsplus.com/tutorials/using-nodes-event-module--net-35941
* Code for geek on event emitters: https://codeforgeek.com/2014/11/eventemitter-node-js/
* Nodejs documentation on events: https://nodejs.org/api/events.html
* A full before/after example of cleaning up nested functions using event emitters: http://rob.conery.io/2012/04/05/cleaning-up-deep-callback-nesting-with-nodes-eventemitter/
