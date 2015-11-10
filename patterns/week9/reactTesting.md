#React Testing

It’s possible to do both unit tests and continuous integration tests with React, but they require slightly different approaches.

###Unit Testing:

Shallow rendering is very useful for unit testing as you can render a component one level deep  without worrying about the effects (or bugs!) of the child components. You can still look at the immediate child components one level down but they are only represented as objects, not rendered. This is useful to see if the parent component you are testing is creating its children correctly with the right props and state.



Here’s a short example of how to run shallow rendering tests using tape:
Have a read of the documentation on using reacts’ test utils and shallow rendering, its very short: https://facebook.github.io/react/docs/test-utils.html#shallow-rendering 

Now follow these steps below.


1
```
npm install babel-cli babel-present-react babel-preset-es2015 react@latest --save
npm install tape --save-dev
```

2
```
create .babelrc file and add the following to it:
```
{
“presets”:[“es2015”,”react”]

First create your own appTest.js file and do the following: 

```
var test = require('tape');
var React = require('react');
var ReactTestUtils = require('react-addons-test-utils');
var App = require(<PATH TO YOUR COMPONENTS FILE>);
var shallowRenderer = ReactTestUtils.createRenderer();
shallowRenderer.render(React.createElement(App));
var out = shallowRenderer.getRenderOutput();
```
at this point we advise using `console.log('whole object', out)`, to see what you are getting back so you can test for various aspects.


now test for something like below!

```
test('out first react test!!!!', function(tester) {
tester.equal(out.type, 'div', 'woo! we have a div');
tester.end()

})

}
```
Run Test using `babel-node <YOURTESTFILEPATH>`

