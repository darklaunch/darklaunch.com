To check if a date is greater than today in JavaScript, use the following:

```javascript
var day = '15';
var month = '01';
var year = '2013';
var date = new Date( year, month - 1, day );
var today = new Date();

if (!(date > today)) {
    console.log('date', date, 'is not greater than today', today);
} else {
    console.log('date', date, 'is greater than today', today);
}
```

Note that the values for month in `Date()` are from 0 to 11.

---

Posted Dec 30, 2013.

https://www.darklaunch.com/2013/12/30/javascript-validate-date-is-greater-than-current-date.html