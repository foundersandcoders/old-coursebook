# Data fetching, NPM publishing, and SEMVER

## Data Fetching: How and when to make requests

This tutorial is guide to an API request to Github to get a users information

###Step 1: First you will need to set-up a basic React environment

Hint  you can find one [here]

###Step 2: Create a GithubUsers component.

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

###Step 3: enter your component in your API 

componentDidMount 

## Semantic Versioning

http://semver.org/

##References

https://github.com/FAC6/book/edit/master/patterns/week8/react_requests.md
