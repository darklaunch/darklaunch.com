# JavaScript class

Here is a JavaScript class example.

```javascript
'use strict';

class MyClass {
    static get CHARACTER_TO_NUMBER() {
        return {
            'a': 1,
            'b': 2,
            'c': 3,
        };
    }

    options = {};

    publicVariable = 'some public value';
    #privateVariable = 'some private value';

    constructor(options) {
        console.info('MyClass.constructor');
        console.log('MyClass.constructor.options:', options);
        this.options = options;
        this.displayOptions();

        console.log('this.privateVariable:', this.#privateVariable);
    }

    getCharacterFromNumber(number) {
        console.info('MyClass.getCharacterFromNumber');
        console.log('MyClass.getCharacterFromNumber.number:', number);
        var character = MyClass.CHARACTER_TO_NUMBER[number];
        console.log('MyClass.getCharacterFromNumber.character:', character);
        return character;
    }

    displayOptions() {
        console.info('MyClass.displayOptions');
        console.log('this.options:', this.options);
    }
}

var mc = new MyClass({
    'debug': true,
    'some_option': 'some_value',
});

var result = mc.getCharacterFromNumber('b');
console.log('mc.result:', result);
console.log('mc.publicVariable:', mc.publicVariable);
```

Output:

```javascript
MyClass.constructor
MyClass.constructor.options: { debug: true, some_option: 'some_value' }
MyClass.displayOptions
this.options: { debug: true, some_option: 'some_value' }
this.privateVariable: some private value
MyClass.getCharacterFromNumber
MyClass.getCharacterFromNumber.number: b
MyClass.getCharacterFromNumber.character: 2
mc.result: 2
mc.publicVariable: some public value
```

---

Posted Nov 19, 2019.

https://www.darklaunch.com/2019/11/19/javascript-class.html