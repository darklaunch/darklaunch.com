Use Array.concat() to merge multiple JSON objects.
```javascript
var first = [
    {
        'a': 1,
        'b': 2,
    }
];
var second = [
    {
        'c': 3,
        'd': 4,
    }
];
var combined = first.concat(second);
console.log(JSON.stringify(combined, null, 2));
```
```
[
  {
    "a": 1,
    "b": 2
  },
  {
    "c": 3,
    "d": 4
  }
]
```