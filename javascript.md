# Javascript

* Always use strict mode with `"use strict";` at the top of every closure (or file).

* Precede all closures with a semicolon.

* Wrap all code in closures (unless you use module.exports)

```
;(function (){
    "use strict";

   //code goes in here

}());

```
### Objects

Use the literal syntax for object creation
    // bad
    var item = new Object();
    // good
    var item = {};

Don't use reserved words as keys. It won't work in IE8.
More info
    // bad
    var superman = {
        default: { clark: 'kent' },
        private: true
    };

    // good
    var superman = {
        defaults: { clark: 'kent' },
        hidden: true
    };

Use readable synonyms in place of reserved words.
    // bad
    var superman = { class: 'alien' };
    // bad
    var superman = { klass: 'alien' };
    // good
    var superman = { type: 'alien' };

### Arrays

#### Best Practice
Use literal syntax:
    //bad
    var items = new Array();
    //good
    var items = [];

Avoid using "new" if possible. It complicates your code:
```
var points = new Array(40, 100);  // Creates an array with two elements (40 and 100)
var points = new Array(40);       // Creates an array with 40 undefined elements
```
When you need to copy an array:
```
// bad
for (i = 0; i < len; i++) itemsCopy[i] = items[i];
// good
itemsCopy = items.slice();
```
For immediately-invoked functions, use (note the slightly different order of the parentheses):
```
//good
(function() {
  // code... again
}());
rather than:
//bad
(function() {
  // code, for the last time
})();
```
All functions should be named, it will help you debug your programs:
```
//bad
function () {...}
//good
function functionName () {...}
```
Name functions in a way that even your grandma can guess what it does:
```
function multiply (number1, number2) {
  alert(number1 * number2);
}
```
Don't declare functions inside an 'if' statement.
```
if (currentUser) function test() { console.log('Nope.'); }
```
Don't use "arguments" as a parameter name, it is a reserved word.

Don't start variable names with numbers.
Don't use dashes or periods in variable names.
Don't use reserved words as variable names.
Don't use multiple variable names with different capitalizations:
```
var name;
var Name;
```

Use descriptive variable names so your grandma could know what is stored in it.

Use camelCase for multi-word variables.
Use one "var" for multiple variables (but be careful to use commas not semi-colons):
```
var items = getItems(),
    goSportsTeam = true,
    dragonball = 'z';
```
Create methods with:
```
objectName.prototype.methodName = function () {...}
```
Use `hasOwnProperty` rather than `in` to check for object properties, unless you have good reason.
```
// bad
if ("Hi" in myObj) {...}
// good
if (myObj.hasOwnProperty("Hi")) {...}
```
Similarly, qualify your `for-in` loops with a `hasOwnProperty` check
```
for (var prop in myObj) {
    if (myObj.hasOwnProperty(prop)) {
        //body
    }
}
```
Conditional statements should be formatted like this (note single space and no line break between curly brace and "else"):
```
if (condition) {
   //body
} else {
   //body
}
```
Comment above the code it refers to:
    // bad
    var active = true;  // is current tab
    // good
    // is current tab
    var active = true;

Use multi-line comments to describe inputs and outputs of functions:

    // bad
    // make() returns a new element
    // based on the passed in tag name
    //
    // @param <String> tag
    // @return <Element> element

    // good
    /**
     * make() returns a new element
     * based on the passed in tag name
     *
     * @param <String> tag
     * @return <Element> element
     */

Prefix comments with FIXME and TODO to help other developers understand what the comment refers to.
```
  function Calculator() {
    // FIXME: shouldn't use a global here
    total = 0;
    return this;
  }
  function Calculator() {
    // TODO: total should be configurable by an options param
    this.total = 0;
    return this;
  }
```
Chain methods like this:
```
originalFunction()
    .method1()
    .method2();
```
Use plain Javascript instead of JQuery when possible.
