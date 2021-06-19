# JavaScript format string

JavaScript format string similarly to python's string format.

```javascript
String.format = function(format) {
    var args = Array.prototype.slice.call(arguments, 1);
    return format.replace(/{(\d+)}/g, function(match, number) {
        return typeof args[number] != 'undefined' ? args[number] : match;
    });
};
```

https://docs.python.org/3/library/stdtypes.html#str.format
http://stackoverflow.com/questions/610406/

---

Posted Apr 2, 2015.

https://www.darklaunch.com/2015/04/02/javascript-format-string.html