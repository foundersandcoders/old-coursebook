# Code Refactoring
## What is it?
Code refactoring is the process of restructuring existing
 computer code – changing the factoring – without changing its external behavior.

## Why?
Refactoring improves code readability and simplicity.
The person who benefits most from refactoring is your coworker, the person who has to read your code, understand it and add new features.
In addition, if you do want to change the codes functionality, it is much easier to do
once the code has been simplified (refactored).Code simplicity, manageability is paramount to productivity.

## When to refactor?

* Duplication
* Long methods - perhaps more than 10 lines long - stop and think if you can make it shorter.
* Switch/ if statements - are they getting too long and complex
* Speculative code (code that you might need - best to remove it)
* Comments - often used to hide messy code

## Methods
<img src="https://upload.wikimedia.org/wikipedia/commons/d/d5/Rubber_duck_assisting_with_debugging.jpg" width="200px" height="200px" />

Refactoring is usually done in small steps. After each small step, you're left with a system that's functionally unchanged.

A sophisticated example of code debugging is the Rubber duck method, pictured above:

1. find rubber duck
2. explain to rubber duck every line of your code
3. find the problem
4. solve it

## Background Reading
[General information](http://c2.com/cgi/wiki?WhatIsRefactoring)
