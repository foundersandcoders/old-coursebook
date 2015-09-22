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
