Bind a function to the hash change event.

```javascript
function hashChange() {
    console.info('hash changed!');
}

window.addEventListener('hashchange', hashChange, false);
```