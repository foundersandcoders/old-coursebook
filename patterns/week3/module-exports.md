# HOW DOES module.exports WORK?

module.exports is the object that is actually returned as the result of a 'require'
call.

### WHAT IS A MODULE?

A module groups together a body of code and makes it available as a single unit
which can be accessed by other files. For example a file with many functions
within it can be encapsulated and then exported, ready to be used when 'required'.

An example of a module would be:

```javascript
// within myModule.js

var exports = module.exports

var myFunction1 = function(){ ... }
var myFunction2 = function(){ ... }

exports.myFunction1 = myFunction1;
exports.myFunction2 = myFunciton2;
```

### HOW TO REQUIRE A MODULE

In order to 'require' a module you must write this within the file where you want
to use the module:

```javascript
//within main.js
var module = require('myModule');
```

This gives you access to the functions in myModule, for example, if I wanted to
use myFunc1 I would write:

```javascript
module.myFunction1();
```

It's worth noting that the name added to the exports object does not have to be
the same as the module's internally scoped name, so instead you could have:

```javascript
var myFunction1 = function(){ ... };
exports.func1 = myFunction1;
```
