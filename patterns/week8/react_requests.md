# Data fetching, NPM publishing, and SEMVER

## Data Fetching: How and when to make requests

This tutorial is guide to an API request to Github to get a users information

###Step 1: First you will need to set-up a basic React environment

Hint  you can find one [here]

###Step 2: Create a GithubUsers component.

We have created a file for each seperate component and exported this.

```javascript 

var React = require('react');

var GithubUser = React.createClass({

	getInitialState: function() {
	    return {
	      username: 'vadda',
	      userUrl: 'bong'
	    };
	},

	  componentDidMount: function() {
	       var request = new XMLHttpRequest();
	     
	      request.onreadystatechange = function() {
	          var user = JSON.parse(request.responseText);
	        
	          if (this.isMounted()) {
	          	  this.setState({
	                  username: user.login,
	                  userUrl: user.html_url
	              })

	          }
	      }.bind(this)
	    
	      request.open('GET', this.props.src);
	      request.send();

	  },

     render: function() {
	    return (<a href={this.state.userUrl}>{this.state.username}</a>)
	  }

});
    
module.exports =  GithubUser;
```
##### Points to note regarding this code are:

```componentDidMount``` is a method of React which is automaticaly called when the component is rendered.
``this.isMounted()``` This indicates that the component ```this`` is has been mounted to the DOM . 
```this.setState()``` This defines the dynamic state of the component by assiging values to the keys in the 'state' object which you have defined in the ```getInitialState()``` function.
```render()``` function will display the output of the repsonse on your UI. 

###Step 3: Entering your component into your app for rendering. 

In our example we use an 'app.js' file where we require each component and set the properties and states specific to that page.  

```javascript

var React = require('react');
var Header =require('./Header.js');
var List= require('./List.js');
var Listbox = require('./Listbox.js');
var Footer =require('./Footer.js');
var GitHubUser = require('./GitHubUser.js');


var App = React.createClass({


  getInitialState: function () {
    return {
       
       items:["oranges","chicken","milk","hairy-baws","apples"]

    };
  },

render: function () {

    return (
      <div className='app-container' >
        <Header title="Fridge" />
        <List items={this.state.items} />
        <Listbox placeholder="Enter your food"/>
        <GitHubUser src="https://api.github.com/users/sohilpandya"/>
        <Footer name="signature" />
      </div>
    );
  }

});

module.exports = App;

```

####Points to note regarding this code are : 

We require the file './GitHubUsers.js
We use the component ```<GitHubUser src="https://api.github.com/users/sohilpandya"/>``` and include the endpoint in our source which in the component is referred to as the ```this.props.src```.






## Semantic Versioning

http://semver.org/

##References

https://github.com/FAC6/book/edit/master/patterns/week8/react_requests.md
