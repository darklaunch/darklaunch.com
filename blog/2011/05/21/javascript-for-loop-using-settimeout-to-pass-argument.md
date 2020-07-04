<p>When using a for loop with setTimeout, you may encounter unexpected behavior.</p>

<p>Consider the following code. What do you expect the console to display?</p>

<code name="javascript">
var time = 0;
for (var i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function() {
        console.log("var is now", i);
    }, time);
}
</code>

<p>You may have expected this:</p>

<code>
var is now 0
var is now 1
var is now 2
var is now 3
var is now 4
</code>

<p>The code actually results in:</p>

<code>
var is now 5
var is now 5
var is now 5
var is now 5
var is now 5
</code>

<p>The reason is that the code is evaluated at runtime. When the first setTimeout function fires, the referenced variable i is now set to 5; the same is true for the subsequent firings of setTimeout functions.</p>

<h3>Option #1: Use JavaScript Closures</h3>

<p>Use setTimeout with a JavaScript for loop:</p>

<code name="javascript">
var time = 0;
for (var i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function(j) {
        return function() {
            console.log("var is now", j);
        }
    }(i), time);
}
</code>

<h3>Option #2: Replace var with let</h3>

<p>Replace "var" with "let". Unlike the "var" keyword, which defines a variable globally, using "let" declares a block scope local variable. Each iteration causes a separate instance of the variable.</p>

<code name="javascript">
var time = 0;
for (let i = 0; i < 5; i++) {
    time += 1000;
    setTimeout(function() {
        console.log("var is now", i);
    }, time);
}
</code>