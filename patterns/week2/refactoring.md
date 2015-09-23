# REFACTORING! 

## What is it?

Refactoring is a disciplined technique for restructuring an *existing* body of code, altering its internal structure without changing its external behaviour.

## When would you want to do it? 

The purpose of refactoring is to improve the quality, clarity and maintainability of your code. 

> By continuously improving the design of code, we make it easier and easier to work with. This is in sharp contrast to what typically happens: little refactoring and a great deal of attention paid to expediently adding new features. If you get into the hygienic habit of refactoring continuously, you'll find that it is easier to extend and maintain code.
— Joshua Kerievsky, Refactoring to Patterns

If you inherit a poorly designed code base that you've not seen before and you now need to either fix a bug or add a new feature, then implementing the code necessary would be a lot easier once you had refactored it to be in a more stable, maintainable and ultimately 'understandable' state.

**Therefore** - you'll probably find that you refactor when you want to fix a bug or add a new feature, because you need to *understand* the code that's been before! The process will clean up your previous code and help you understand it far better.

A lot of the time people will only consider refactoring at the beginning or end of a project, but it should be done in small chunks *continuously* throughout a project. 

## Why else would you want to do it? 

Refactoring produces clean code, as mentioned above. Clean code is good code. Clean code:

 * Passes all tests.
 * Is obvious for other programmers.
 * Does not contain duplication.
 * Contains a minimum number of classes and other moving parts.

It's also *easier* to work with and *cheaper* to maintain. 

## How do you do it?

Refactoring is best performed as a series of *minor* changes. Each change improves the existing code slightly while keeping it in functional condition.

Three key components of correct refactoring:

1. No new functionality is created during refactoring
2. All existing tests should be successfully passed after refactoring
3. The code becomes simpler after refactoring

Refactoring catalogue [here](https://refactoring.guru/catalog)

