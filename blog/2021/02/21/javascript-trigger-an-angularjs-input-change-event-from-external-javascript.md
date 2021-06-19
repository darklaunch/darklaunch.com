# JavaScript trigger an AngularJS input change event from external JavaScript

Use the `dispatchEvent` JavaScript function to trigger a form field`s input event on a page that is using Angular.

This "input" trigger event was needed on an Angular 9.1.12 page:

```javascript
function triggerInput(element) {
    element.dispatchEvent(
        new window.Event('input', { bubbles: true })
    );
}
```

Usage:

```javascript
var nameInputField = document.querySelector('#name');
nameInputField.value = 'Alice';
triggerInput(nameInputField);
```

Other events may be similarly triggered:

```javascript
function triggerMouseEvent(element, eventType) {
    var clickEvent = document.createEvent('MouseEvents');
    clickEvent.initEvent(eventType, true, true);
    element.dispatchEvent(clickEvent);
}

var myButton = document.querySelector('button');
triggerMouseEvent(myButton, 'mousedown');
triggerMouseEvent(myButton, 'mouseup');
```

---

Posted Feb 21, 2021.

https://www.darklaunch.com/2021/02/21/javascript-trigger-an-angularjs-input-change-event-from-external-javascript.html