The typeof operator will say that an array is an "object". To accurately identify an array from an object in JavaScript, use the following solution:
```javascript
function isArray(var) {
    return Object.prototype.toString.apply(var) === "[object Array]";
}
```

Instead of using typeof or instanceof, use the Object.prototype.toString.apply method to check if a variable is an object or is an array in JavaScript.
```javascript
Object.prototype.toString.apply( $("body") )
// "[object Object]"

Object.prototype.toString.apply( [{foo:"bar"}] )
// "[object Array]"
```

As an alternate solution, use the toString.call(element) method.
```javascript
toString.call( $("body") )
// "[object Object]"

toString.call( [{foo:"bar"}] )
// "[object Array]"
```

jQuery type, isArray and isPlainObject functions are also available.
```javascript
$.type(element)
$.isArray(element)
$.isPlainObject(element)
```
```javascript
$.type( [{foo:"bar"}] )
// "array"

$.type( $("body") )
// "object"
```
```javascript
$.isArray( [{foo:"bar"}] )
// true

$.isArray( $("body") )
// false
```
