View a string's newlines and tabs in JavaScript. This function replaces line endings/newlines and tabs:
```javascript
function raw(str) {
    return str.replace(/\t/g, '\\t')
              .replace(/\r\n/g, '\\r\\n')
              .replace(/\r/g, '\\r')
              .replace(/\n/g, '\\n');
}
```
The /g modifier finds and replaces all occurrences.