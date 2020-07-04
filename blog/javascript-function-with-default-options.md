Use Object.assign to merge objects.
```javascript
const original = {
    'a': 1,
    'b': 2,
    'c': 0,
};

const updates = {
    'c': 3,
    'd': 4,
};

const result = Object.assign(original, updates);
console.log('result:', result);
```
```
result: { a: 1, b: 2, c: 3, d: 4 }
```

Create a function that has default options by using Object.assign.
```javascript
function doThing(options) {
    var defaults = {
        'debug': false,
        'retryCount': 0,
    };
    options = Object.assign(defaults, options);
    console.log(options);
}
```
```javascript
doThing();
// { debug: false, retryCount: 0 }

doThing({'debug': false, 'retryCount': 1});
// { debug: false, retryCount: 1 }

doThing({'debug': true, 'retryCount': 5});
// { debug: true, retryCount: 5 }
```