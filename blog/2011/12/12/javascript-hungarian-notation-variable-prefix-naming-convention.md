Hungarian Notation is a language agnostic naming convention that prefixes variables with the variable's type. This allows the reader to determine the type and use of a variable by such an identifier.

JavaScript Hungarian Prefixes:

* a - array
* b - boolean
* f - float
* fn - function
* i - integer
* n - node
* o - object
* s - string

```javascript
var aData = [1, 2, 3];
var bFound = false;
var fGoldenRatio = 1.618;
var fnCallback = function() { };
var iCurrentPage = 1;
var nNewRow = document.createElement("tr");
var oSettings = {
    type: "GET",
    url: "test.json",
    dataType: "jsonp"
};
var sLabel = "First Name";
```

Prefixes may also be combined where appropriate.

```javascript
var asData = "foo,bar,baz".split(","); // Array of type String.
```

Examples in other languages:

```cpp
int iNumber = 2;
```

```php
$sQuote = "Imagination is more important than knowledge.";
```

```autoit
$sMsg = "Example message string."
```

---


Posted Dec 12, 2011.
https://www.darklaunch.com/2011/12/12/javascript-hungarian-notation-variable-prefix-naming-convention.html