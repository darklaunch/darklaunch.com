# jQuery find first empty form field using the :input selector

Find the first empty form field in JavaScript using jQuery with the example below.

```javascript
var myform = $("form");
var firstEmptyField = myform.find(":input[value='']:visible").not("button").filter(":first")
console.log("the first empty field: ", firstEmptyField);
```

---

Posted Jun 28, 2011.

https://www.darklaunch.com/2011/06/28/jquery-find-first-empty-form-field-using-the-input-selector.html

---

1 comment

<ol><li><div>

anonymous &ndash; Dec 4, 2011<div>

Very nice site!

</div></div></li></ol>