Using Date with JavaScript might unexpectedly return the value 1 instead of 31. Fix this by doing the following:

```javascript
var input = '2020-06-01'

// Incorrect:
var eventDate = new Date(input);
var result = eventDate.toLocaleString('default', { month: 'short' }) + ' ' + eventDate.getUTCDate() + ', ' + eventDate.getUTCFullYear()
console.log('result:', result);
// result: May 1, 2020

// Correct:
var eventDate = new Date(input);
var result = eventDate.toLocaleString('default', { month: 'short' }) + ' ' + eventDate.getDate() + ', ' + eventDate.getFullYear();
console.log('result:', result);
// result: May 31, 2020
```

---

Posted Oct 21, 2020.

https://www.darklaunch.com/2020/10/21/fix-javascript-date-returning-1-instead-of-31.html