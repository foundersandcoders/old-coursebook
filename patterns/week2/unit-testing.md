# What is Unit Testing?

## Unit Testing

Individual units of source code are tested to determine whether they are fit for use.One can view a unit as the smallest testable part of an application.

The units should be tested according to the following criteria:

* to ensure units are error free
* to ensure units' efficiency
* ensure unit's code meets its design and behaves as intended

These unit tests encourage developers to modify the source code without immediate concerns about how such changes might affect the functioning of other units or the program as a whole.

####Problems without Unit Testing

A general lack of structure;  in anonymous functions that can’t be tested because they aren’t exposed.

Complex functions; if a function is more than 10 lines, like the submit handler, it’s highly likely that it’s doing too much.

Hidden or shared state; for example, as variables might be in a closure, there’s no way to test whether they are set correctly.


####Benefits

1. Unit Testing reduces the level of bugs in production code.
2. Automated tests can be run as frequently as required.
3. Unit Testing makes it easier to change and refactor code.
4. Unit Testing can improve the design of code especially with Test-Driven Development.
5. Unit Tests are a form of documentation.
6. Unit Tests are a measure of completion.
7. Simplifies integration
8. Unit Testing is F - U - N !!!?

Unit testing facilitates the writing of a greater number of smaller, more focused functions that provide a single operation on a set of data. Without unit testing functions tend to be larger and each would perform a number of different operations.

In TDD unit tests are created before the code itself is written. When the tests pass, that code is considered complete.


#### Integration Testing

Once the tests have been satisfied they are the units of code are then combined and integration testing begins. In integration testing, the units are combined and tested as a group.

### Example - What makes a Good Unit Test? The Stopwatch Example


* Represent each distinct piece of behavior as a separate object that falls into one of the four areas of responsibility and doesn’t need to know about other objects. This will help us avoid creating tangled code.
* Support configurability, rather than hard-coding things. This will prevent us from replicating our entire HTML environment in order to write our tests.
* Keep our objects’ methods simple and brief. This will help us keep our tests simple and our code easy to read.
* Use constructor functions to create instances of objects. This will make it possible to create “clean” copies of each piece of code for the sake of testing.


One example of a unit test is separating the clear button functionality from the rest of the stopwatch. The alternative would be to incoporate clear functionality in the 'counting' function.


```
function clear(){
  timeElapsed = 0;
  element.innerhtml = timeElapsed;
  return timeElapsed;
}
```


```
test('The timer clears when the button is pushed', function(assert) {
  var clearTest = T.clear();
  assert.equal(clearTest, 0, 'Message: timer is zero at start' );
});
```

A great worked example using jquery can be found on the following blog post:

http://alistapart.com/article/writing-testable-javascript
