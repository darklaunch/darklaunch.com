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
<!doctype html>
<html>
<head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8" />
    <script src="//ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
    <title></title>
</head>
<body>

<!-- Example 1 -->
<select id="select-1">
    <option>Select an option...</option>
    <option value="1">Foo</option>
    <option value="2">Bar</option>
    <option value="3">Baz</option>
</select>

<script>
// Select the option using the option's exact text value
var selectOptionText = "Baz";
$("#select-1").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).attr("selected", "selected");
</script>
<!-- /Example 1 -->

<!-- Example 2 -->
<select id="select-2">
    <option>Pick a different option...</option>
    <option value="5">Wibble</option>
    <option value="6">wobble</option>
    <option value="7">wubble</option>
    <option value="8">flob</option>
</select>

<script>
// Select the option using the option's exact text value
var selectOptionText = "wobble";
$("#select-2").find("option").filter(function(index) {
    return selectOptionText === $(this).text();
}).prop("selected", "selected");
// NOTE: As of jQuery 1.6, use the $.prop() method to retrieve property values because $.attr() only retrieves attributes.
</script>
<!-- /Example 2 -->

</body>
</html>
```

---

Posted May 20, 2011.

https://www.darklaunch.com/2011/05/20/jquery-select-option-using-text-value-text.html

---

7 comments

<ol><li><div>

anonymous &ndash; Sep 28, 2011<div>

:contains is not ideal, consider some of the values might be cintained within others.Eg, if you got an option with "bble" as text and you want the id,
@$("select:last").find("option:contains('bble')").prop("selected", "selected") will return more than one

</div></div></li><li><div>

anonymous &ndash; Jan 30, 2012<div>

click the option value change to provide new value

</div></div></li><li><div>

anonymous &ndash; May 24, 2012<div>

Thanks :D

</div></div></li><li><div>

anonymous &ndash; Dec 29, 2012<div>

Contains returns all the options which contain the searched string. It is not an exact match.

</div></div></li><li><div>

anonymous &ndash; Jan 3, 2013<div>

Examples have been updated! Use the $.filter() method for an exact match.

</div></div></li><li><div>

anonymous &ndash; Jan 23, 2013<div>

thanks a lot!
i just find my old selector "option[text='s3']" does not work.

</div></div></li><li><div>

anonymous &ndash; Jul 22, 2013<div>

nice :)

</div></div></li></ol>