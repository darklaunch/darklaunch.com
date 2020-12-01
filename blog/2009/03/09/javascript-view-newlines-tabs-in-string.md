View a string's newlines and tabs in JavaScript. This function replaces line endings/newlines and tabs:

```javascript
function raw(str) {
    return str.replace(/\t/g, '\\t')
              .replace(/\r\n/g, '\\r\\n')
              .replace(/\r/g, '\\r')
              .replace(/\n/g, '\\n');
}
```

The `/g` modifier finds and replaces all occurrences.

---

Posted Mar 9, 2009.

https://www.darklaunch.com/2009/03/09/javascript-view-newlines-tabs-in-string.html