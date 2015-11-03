# react-test-tutorial

## Testing React

### Testing using Jest

Jest is a testing framework that you'll need to figure out how to use. Follow this tutorial to install and run Jest __exactly__. For example, your testing folder has to be called tests
with two underscores or it won't work and jest won't know what to look for:
```
__tests__
```
Link here > jest (https://facebook.github.io/jest/docs/getting-started.html#content)

### Testing React

To test React Facebook use the NPM module: react-addons-test-utils

You'll need to require this at the top of your file.
```
var ReactTestUtils = require('react-addons-test-utils')
```
It lets you change react components in your tests.

The package.json file found in the setup section of this tutorial provides all the modules that are necessary for jest test 2015.
https://facebook.github.io/jest/docs/tutorial-react.html#content

### Recommended Reading

Testing DOM elements rendered with React:
https://facebook.github.io/react/docs/test-utils.html

Introduction to testing using Jest:
https://facebook.github.io/jest/docs/tutorial-react.html#content

Alternative React testing framework called Karma:
https://github.com/besarthoxhaj/testing-react/blob/master/test/hello.js
