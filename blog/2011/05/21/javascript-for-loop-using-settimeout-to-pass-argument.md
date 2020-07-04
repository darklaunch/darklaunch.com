When using a for loop with setTimeout, you may encounter unexpected behavior.

Consider the following code. What do you expect the console to display?
```javascript
var time = 0;
for (var i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function() {
        console.log("var is now", i);
    }, time);
}
```
You may have expected this:
```
var is now 0
var is now 1
var is now 2
var is now 3
var is now 4
```
The code actually results in:
```
var is now 5
var is now 5
var is now 5
var is now 5
var is now 5
```
The reason is that the code is evaluated at runtime. When the first setTimeout function fires, the referenced variable i is now set to 5; the same is true for the subsequent firings of setTimeout functions.

### Option #1: Use JavaScript Closures

Use setTimeout with a JavaScript for loop:
```javascript
var time = 0;
for (var i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function(j) {
        return function() {
            console.log("var is now", j);
        }
    }(i), time);
}
```
### Option #2: Replace var with let

Replace "var" with "let". Unlike the "var" keyword, which defines a variable globally, using "let" declares a block scope local variable. Each iteration causes a separate instance of the variable.
```javascript
var time = 0;
for (let i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function() {
        console.log("var is now", i);
    }, time);
}
```