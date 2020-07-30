Determine if an element is effectively hidden in JavaScript.

```javascript
function isHidden(e) {
    const style = window.getComputedStyle(e);
    if (
        style.display === 'none' ||
        style.opacity === '0' ||
        style.fontSize === '0px' ||
        style.visibility === 'hidden'
    ) {
        return true;
    }
    return false;
}
```

from https://github.com/tiratatp/facebook_adblock/blob/master/src/main.js

---

Posted Jan 10, 2020.
https://www.darklaunch.com/2020/01/10/javascript-function-ishidden