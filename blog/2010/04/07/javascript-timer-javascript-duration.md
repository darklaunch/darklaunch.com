To time and measure the duration of a JavaScript event.

```js
function start() {
    startTime = new Date().getTime();
}

function stop() {
    var endTime = new Date().getTime();
    return endTime - startTime;
}
```

Example:
```js
function start() {
    startTime = new Date().getTime();
}

function stop() {
    var endTime = new Date().getTime();
    return endTime - startTime;
}

function doSomething() {
    for (var i = 0; i < 1000000; i++) {
        // Do something
    }
}
```

```html
<input value="Click me" onclick="start(); doSomething(); alert(stop() + 'ms');" type="button" />
```

---

Posted Apr 7, 2010.
https://www.darklaunch.com/2010/04/07/javascript-timer-javascript-duration