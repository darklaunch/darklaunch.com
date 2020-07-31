Add inline css style using JavaScript via document.createElement.

```javascript
var style = document.createElement('style');
style.textContent = '.alert { color: red; };';
document.head.appendChild(style);
```

---


Posted Feb 24, 2016.
https://www.darklaunch.com/2016/02/24/add-css-inline-style-using-javascript.html