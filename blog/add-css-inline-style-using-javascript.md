Add inline css style using JavaScript via document.createElement.
```javascript
var style = document.createElement('style');
style.textContent = '.alert { color: red; };';
document.head.appendChild(style);
```