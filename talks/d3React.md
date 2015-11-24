Links from a talk by Andreas who works at Twitter and is working on Victory JS.

Good resources to read on what people have done in terms of combining d3
with React:

["D3 and React - The future of charting components?"](http://10consulting.com/2014/02/19/d3-plus-reactjs-for-charting) by 10 consulting.


["Integrating D3.js visualizations in a React app"](http://nicolashery.com/integrating-d3js-visualizations-in-a-react-app) by Nicolas Hery


["ReactJS and D3 Part I: Layouts"](http://formidable.com/blog/2015/05/21/react-d3-layouts) by Colin Megill

In the context of re-writing an existing application that's written in something else other than React (for example Backbone, Angular or Ember),
this talk by [Ryan Florence](https://twitter.com/ryanflorence) , who is the
co-author of [React Router](https://github.com/rackt/react-router) is
really good to watch:

https://www.youtube.com/watch?v=BF58ZJ1ZQxY

If you want to use classes and sleep at night, you should read [Dan Abramov](https://twitter.com/dan_abramov)'s Medium post, ["How to Use Classes and
Sleep at Night"](https://medium.com/@dan_abramov/how-to-use-classes-and-sleep-at-night-9af8de78ccb4)



The base repository for Victory.js is [here](https://github.com/FormidableLabs/victory), you should also have a look at
the [Formidable Labs GitHub organization](https://github.com/FormidableLabs)
though to see everything they have.

While you are at it, you should check
out [Radium](https://github.com/FormidableLabs/radium) for inline styles;
you know the default inline styling you can do in React? This is that but
on steroids.

You can specify how things should change on hover for example in a very easy and concise way.
You should watch this talk by [Sebastian Markbage](https://twitter.com/sebmarkbage), one of the core engineers at Facebook working on React, where he talks about his/Facebook's vision for web standards, the DOM and other such things:
https://www.youtube.com/watch?v=3DZemce4Y1Y-A


If you have used React Router in the past, before the release of v1.0.0, and wish to migrate to using v1.0.0, have a look at [CHANGES.md](https://github.com/rackt/react-router/blob/master/CHANGES.md) on their repository which has an upgrade guide as well.

In terms of testing, like I mentioned, use [Shallow Rendering](https://facebook.github.io/react/docs/test-utils.html#shallow-rendering) -
this is Facebook's recommendation as per their core React developers as you
can read [here](https://discuss.reactjs.org/t/whats-the-prefered-way-to-test-react-js-components/26/2)
and [here](https://twitter.com/sebmarkbage/status/642376876070207488)
