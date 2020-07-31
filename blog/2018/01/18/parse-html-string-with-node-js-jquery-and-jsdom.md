Parse an html string using Node.js, jQuery, and jsdom.

Install jsdom and jquery.

```javascript
$ npm install jsdom
$ npm install jquery
```

Write JavaScript file.

```javascript
var jsdom = require('jsdom');
var dom = new jsdom.JSDOM();
var window = dom.window;
var document = window.document;

var $ = require('jquery')(window);
console.log('version:', $.fn.jquery);

var $content = $('<a href="https://www.example.com/">Link</a>');
console.log('text:', $content.text());
console.log('html:', $content.html());
console.log('href:', $content.find('a').attr('href'));
```

Run JavaScript file.

```bash
$ node script.js
version: 3.2.1
text: Link
html: <a href="https://www.example.com/">Link</a>
href: https://www.example.com/
```

---

Posted Jan 18, 2018.

https://www.darklaunch.com/2018/01/18/parse-html-string-with-node-js-jquery-and-jsdom.html