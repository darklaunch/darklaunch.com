Bind to `window.onkeydown` natively without jQuery.

```javascript
window.onkeydown = function(event) {
    if (event.keyCode === 27) {
        console.log('escape pressed');
    }
};
```

---

Posted Aug 5, 2014.
https://www.darklaunch.com/2014/08/05/javascript-window-onkeydown-without-jquery