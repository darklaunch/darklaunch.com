# JavaScript startsWith function string, characters

JavaScript starts with a string.

```javascript
function startsWith(data, input) {
    return data.substring(0, input.length) === input;
}

String.prototype.startsWith = function (input) {
    return this.substring(0, input.length) === input;
};
```

```javascript
var url = "https://www.example.com/";

console.assert(url.startsWith("https://") === true);
console.assert(url.startsWith("http://") === false);
console.assert(startsWith(url, "https://") === true);
console.assert(startsWith(url, "http://") === false);
```

---

Posted Jan 18, 2013.

https://www.darklaunch.com/2013/01/18/javascript-startswith-function-string-characters.html

---

1 comment

<ol><li><div>

anonymous &ndash; Apr 4, 2013<div>

good

</div></div></li></ol>