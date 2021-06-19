# JavaScript Iframe Killer

JavaScript iframe killer

```javascript
// iframe killer
while ((el=document.getElementsByTagName('iframe')).length) {
    el[0].parentNode.removeChild(el[0]);
}
```

---

Posted Feb 5, 2009.

https://www.darklaunch.com/2009/02/05/javascript-iframe-killer.html