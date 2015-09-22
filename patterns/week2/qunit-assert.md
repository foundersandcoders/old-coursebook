#Qunits Assertion

When writing unit test with Qunit there are serveral assertion methods you can use based on the specific characteristics of your code. 


Test syntax
```
QUnit.test( "assert.async() test", function( assert ) {
  var input = $( "#test-input" ).focus();
  setTimeout(function() {
    assert.equal( document.activeElement, input[0]/*Expected outcome*/, "Input was focused"/*message to tester */ );
  });
});
```



##Async Asserts
This allows you to test asynchronously within a period of time, see below and documentation (

```
QUnit.test( "assert.async() test", function( assert ) {
  var done = assert.async();
  var input = $( "#test-input" ).focus();
  setTimeout(function() {
    assert.equal( document.activeElement, input[0], "Input was focused" );
    done();
  }//can add an optional figure to timeout);
});
```
##deepEqaul()

assert.deepEqual()

A deep recursive comparison, working on primitive types ( types except Objects are immutable/primitive and can be changed), arrays, objects, regular expressions, dates and functions. The assertion will go deep into the object and match key and value.

##equals()
```assert.equals()
```

The equal assertion uses the simple comparison operator ```(==)``` to compare the actual and expected arguments. When they are equal, the assertion passes; otherwise, it fails. When it fails, both actual and expected values are displayed in the test result, in addition to a given message.
```
QUnit.test( "equal test", function( assert ) {
  assert.equal( 0, 0, "Zero, Zero; equal succeeds" );
  assert.equal( "", 0, "Empty, Zero; equal succeeds" );
  assert.equal( "", "", "Empty, Empty; equal succeeds" );
 
  assert.equal( "three", 3, "Three, 3; equal fails" );
  assert.equal( null, false, "null, false; equal fails" );
});
```
##What's the difference ?

The difference being that ``assert.equal()`` uses the operator ``(==)`` to compare but when two objects which hold the same values are compared they will return ``false``, as they are not the same specific object. Where as with ```deep.equal()``` this goes to the primitive values within in the object to make the comparison and if the elements are the same will return ```true```. This can be seen in the examples below.

```
var a = [1,2,3]  
var b = a              // As a and b both refer to the same object
a == b                 // this is true
a === b                // and this is also true

a = [1,2,3]            // here a and b have equivalent contents, but do not
b = [1,2,3]            // refer to the same Array object.
a == b                 // Thus this is false.

assert.deepEqual(a, b) // However this passes, as while a and b are not the 
                       // same object, they are still arrays containing 1, 2, 3

assert.deepEqual(1, 1) // Also passes when given equal values

var X = function() {}
a = new X
b = new X
a == b                 // false, not the same object
assert.deepEqual(a, b) // pass, both are unadorned X objects
b.foo = 'bar'
assert.deepEqual(a, b) // fail!
```











