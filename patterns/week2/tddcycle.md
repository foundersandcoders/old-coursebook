## Test-driven development cycle

![image](https://cloud.githubusercontent.com/assets/12072531/10015287/464f94b2-6117-11e5-8b48-19e8ddbc0bb3.png)


1. Add a test;
In test-driven development, each new feature begins with writing a test. To write a test the developer must clearly understand the features and specification and requirements.
developer can write the test in whatever testing framework is appropriate to the software environment. The differentiating feature of test-driven development versus writing unit tests after the code is written:is that it makes the developer focus on the requirements before writing the code.

2. Run all of the tests and see if the new one fails;
This validates that the tests are working correctly, that the new test does not mistakenly pass without requiring any new code, and that the required feature does not already exist.

3. Write some code;
The next step is to write some code that causes the test to pass. The new code written at this stage is not perfect and may, for example, pass the test in an inelegant way. That is acceptable because it will be improved and honed in Step 5.

4. Refactor code;
The growing code base must be cleaned up regularly during test-driven development. New code can be moved from where it was convenient for passing a test to where it more logically belongs. Duplication must be removed. Object, class, module, variable and method names should clearly represent their current purpose and use, as extra functionality is added.

5. Repeat;
Starting with another new test, the cycle is then repeated to push forward the functionality. The size of the steps should always be small, with as few as 1 to 10 edits between each test run. If new code does not rapidly satisfy a new test, or other tests fail unexpectedly, the programmer should undo or revert in preference to excessive debugging.

### Best practices

```javascript
test('when you restart timer not set back to zero', function(assert){
  T.start();
  var done = assert.async();
  setTimeout (function(){
    var result = Math.round(T.getTimeElapsed()/1000);
    assert.equal(result, 4, "Timer has counted four seconds");
    T.stop();
    done();
  }, 1000);
});
```

#### Test structure

Effective layout of a test case ensures all required actions are completed, improves the readability of the test case, and smooths the flow of execution. Consistent structure helps in building a self-documenting test case. A commonly applied structure for test cases has (1) setup, (2) execution, (3) validation, and (4) cleanup.

Setup: Put the overall test system in the state needed to run the test.

Execution: Trigger/drive the Unit Under Test (UUT) i.e. the code and the related tests, to perform the target behaviour and capture all output, such as return values and output parameters. This step is usually very simple.

Validation: Ensure the results of the test are correct. These results may include explicit outputs captured during execution or state changes in the code.

Cleanup: Restore the overall test system to the pre-test state. This restoration permits another test to execute immediately after this one.
