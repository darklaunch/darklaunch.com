JavaScript iframe killer
```javascript
// iframe killer
while ((el=document.getElementsByTagName('iframe')).length) {
    el[0].parentNode.removeChild(el[0]);
}
```