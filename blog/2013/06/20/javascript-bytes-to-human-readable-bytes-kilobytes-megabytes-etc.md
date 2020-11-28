```javascript
function prettySize(bytes) {
    var units = ['bytes', 'kb', 'MB', 'GB', 'TB', 'PB'];
    var e = Math.floor(Math.log(bytes) / Math.log(1024));
    var size = (bytes / Math.pow(1024, Math.floor(e))).toFixed(2);
    var unit = units[e];
    return size + ' ' + unit;
}
```

```javascript
console.log(prettySize('1024'));             // 1.00 kb
console.log(prettySize('10240'));            // 10.00 kb
console.log(prettySize('102400'));           // 100.00 kb
console.log(prettySize('1048576'));          // 1.00 MB
console.log(prettySize('1073741824'));       // 1.00 GB
console.log(prettySize('1099511627776'));    // 1.00 TB
console.log(prettySize('1125899906842624')); // 1.00 PB
```

---

Posted Jun 20, 2013.

https://www.darklaunch.com/2013/06/20/javascript-bytes-to-human-readable-bytes-kilobytes-megabytes-etc.html

---

1 comment

<ol>
    <li>
        <div>
            anonymous &ndash; Jan 19, 2014
            <div>
                <p>Thanks!</p>
            </div>
        </div>
    </li>
</ol>
