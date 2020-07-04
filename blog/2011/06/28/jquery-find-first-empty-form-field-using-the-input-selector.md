<p>Find the first empty form field in JavaScript using jQuery with the example below.</p>

<code name="javascript">
var myform = $("form");
var firstEmptyField = myform.find(":input[value='']:visible").not("button").filter(":first")
console.log("the first empty field: ", firstEmptyField);
</code>