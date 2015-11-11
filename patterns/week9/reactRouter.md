# React Router

React Router is a **routing library module** that can be downloaded from npm, with the source code found here:  

https://github.com/rackt/react-router

It was created by Ryan Florence, who was inspired by [Ember's framework](http://guides.emberjs.com/v1.10.0/routing/).

### Why would you use it :question:

* Really fast rendering for different components
* Can add screens and UI easily
* Nesting is dealt with simply
* Manages back buttons and history locations
* Gives links and routes active classes so you don’t have to :+1:

### How do I use it :question:

First make sure you have required React and ReactDom

```
import React from ‘react’
import { render } from ‘react-dom’
```

Then you require React Router

```
import { Render, Route, Link } from ‘react-router’
```

We then want to create an ```App``` component that will hold all of our elements. We need to add links here to the other components.

```
const App = React.createClass({
	render() {
		return (
			<div>
				<h1>App</h1>
				<ul>
					<li><Link to=”/about”>About</Link></li>
					<li><Link to=”/inbox”>Inbox</Link></li>
				</ul>
				{this.props.children}
/* {this.props.children} is included when a component has nested components within it */
</div>
)
}
})
```

We then render a router with routes for each component

```
render((
	<Router>
		<Route path=’/’ component={App}>
			<Route path=”about” component={About} />
			<Route path=”inbox” component={Inbox}>
				<Route path=”messages/:id” component={Message} />
			</Route>
		</Route>
	</Router>
), document.body)
```


### What other solutions are there to routing in react :question:
Here’s a tutorial on how to build something that works in *pure* react. Advantages are you’re not relying on someone else’s routing api for your app to work:   

http://jamesknelson.com/routing-with-raw-react/

The same person has also written a fairly *basic* react tutorial and **not in es6** if you’re still confused about react generally:

 http://jamesknelson.com/learn-raw-react-no-jsx-flux-es6-webpack/

Another alternative to React Router is **page.js**, made by the same team who made Express:  

 https://github.com/visionmedia/page.js

### Authentication with React Router

React Router has ```onEnter``` and ```onLeave``` hooks that can be defined within the routes. They happen when transitioning between views. Let's cover an example of when the hooks are triggered.

We'll use the example in the first section (above). Say we want to transition from /messages/5 to /about. We have to ```onLeave``` every component between the leaf :leaves: and the first common ancestor branch. We then ```onEnter``` every component until we reach our desired view:

```onLeave``` on the /messages/:id route  
```onLeave``` on the /inbox route  
```onEnter``` on the /about route  

It’s *quite* easy to redirect to a login page if the user isn’t authenticated. Simply add an ```onEnter``` command within the ```<Route>``` of the component that you want to authorize:

```
<Router>
	<Route path=”/” component={App}>
		<Route path=”login” component={Login} />
		<Route path=”dashboard”
			component={Dashboard}
			onEnter={requireAuth} />
	</Route>
</Router>
```

```requireAuth``` is a function that checks if a user is authenticated or not. If not then it redirects to the login view.

```
function requireAuth(next, transition) {
	if(!auth.loggedIn()) {
		transition.to(‘/login’);
}
```

### Additional Reading

Comprehensive Intro to React Router - http://www.themarketingtechnologist.co/react-router-an-introduction/  
Reddit’s take on React Router - https://www.reddit.com/r/reactjs/comments/3ofhg6/an_introduction_to_react_router/  
React Router with Flux - http://jaketrent.com/post/react-router-with-flux/
