# JavaScript: Thousands separator function

To add a comma thousands separator every 3 digits in a number using JavaScript, use the following function:

```javascript
function addThousandsSeparator(value) {
    return value.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
}
```

Example output

```javascript
var list = [
    1,
    1.03,
    10,
    100,
    1000,
    1000.03,
    9000,
    10000,
    100000,
    1000000,
    10000000,
    100000000,
];

for (var i in list) {
    var num = list[i];
    console.log(num, "=>", addThousandsSeparator(num));
}
```

```javascript
// Example output
        1 => '1'
     1.03 => '1.03'
       10 => '10'
      100 => '100'
     1000 => '1,000'
  1000.03 => '1,000.03'
     9000 => '9,000'
    10000 => '10,000'
   100000 => '100,000'
  1000000 => '1,000,000'
 10000000 => '10,000,000'
100000000 => '100,000,000'
```

---

Posted May 9, 2013.

https://www.darklaunch.com/2013/05/09/javascript-thousands-separator-function.html

---

3 comments

<ol><li><div>

anonymous &ndash; May 16, 2014<div>

Note this will break if the number has more than three decimal places!

</div></div></li><li><div>

anonymous &ndash; Jul 25, 2014<div>

This does not work in Safari :(

</div></div></li><li><div>

anonymous &ndash; May 23, 2015<div>

This does not work in Safari :(

</div></div></li></ol>