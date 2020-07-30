I wanted to avoid specifying a max and min.

```javascript
// Math.random(): produces integer -> 0.473239055961688
// toString(): from integer to string -> '0.473239055961688'
// substring(2): extract after period -> '473239055961688'
var str = Math.random().toString().substring(2);
alert(str);
```

This example function requires a max and min.

```javascript
// https://developer.mozilla.org/en/Core_JavaScript_1.5_Reference/Global_Objects/Math/random#Examples
function getRandomInt(min, max){
	return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

---

Posted Feb 20, 2009.
https://www.darklaunch.com/2009/02/20/javascript-random-number-quick-random-number-math-random-substring