<p>Use Object.assign to merge objects.</p>

<code name="javascript">
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
</code>

<code>result: { a: 1, b: 2, c: 3, d: 4 }</code>

<p>Create a function that has default options by using Object.assign.</p>

<code name="javascript">
function doThing(options) {
    var defaults = {
        'debug': false,
        'retryCount': 0,
    };
    options = Object.assign(defaults, options);
    console.log(options);
}
</code>

<code name="javascript">
doThing();
// { debug: false, retryCount: 0 }

doThing({'debug': false, 'retryCount': 1});
// { debug: false, retryCount: 1 }

doThing({'debug': true, 'retryCount': 5});
// { debug: true, retryCount: 5 }
</code>