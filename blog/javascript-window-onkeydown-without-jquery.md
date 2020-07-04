Bind to window.onkeydown natively without jQuery.
```javascript
window.onkeydown = function(event) {
    if (event.keyCode === 27) {
        console.log('escape pressed');
    }
};
```