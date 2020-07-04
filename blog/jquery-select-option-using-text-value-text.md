To select an option by searching for the option's text value, <s>use the :contains selector</s> <ins>use the filter method</ins>.
```javascript
// Select the option using the option's exact text value
var selectOptionText = "Baz";
$("#select-1").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).attr("selected", "selected");
```
As of jQuery 1.6, use $.prop() instead of $.attr().
```javascript
var selectOptionText = "wobble";
$("#select-2").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).prop("selected", "selected");
```
```html
&lt;!doctype html>
&lt;html>
&lt;head>
    &lt;meta http-equiv="content-type" content="text/html; charset=UTF-8" />
    &lt;script src="//ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js">&lt;/script>
    &lt;title>&lt;/title>
&lt;/head>
&lt;body>

&lt;!-- Example 1 -->
&lt;select id="select-1">
    &lt;option>Select an option...&lt;/option>
    &lt;option value="1">Foo&lt;/option>
    &lt;option value="2">Bar&lt;/option>
    &lt;option value="3">Baz&lt;/option>
&lt;/select>

&lt;script>
// Select the option using the option's exact text value
var selectOptionText = "Baz";
$("#select-1").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).attr("selected", "selected");
&lt;/script>
&lt;!-- /Example 1 -->


&lt;!-- Example 2 -->
&lt;select id="select-2">
    &lt;option>Pick a different option...&lt;/option>
    &lt;option value="5">Wibble&lt;/option>
    &lt;option value="6">wobble&lt;/option>
    &lt;option value="7">wubble&lt;/option>
    &lt;option value="8">flob&lt;/option>
&lt;/select>

&lt;script>
// Select the option using the option's exact text value
var selectOptionText = "wobble";
$("#select-2").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).prop("selected", "selected");
// NOTE: As of jQuery 1.6, use the $.prop() method to retrieve property values because $.attr() only retrieves attributes.
&lt;/script>
&lt;!-- /Example 2 -->

&lt;/body>
&lt;/html>
```