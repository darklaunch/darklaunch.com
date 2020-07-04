<p>Parse an html string using Node.js, jQuery, and jsdom.</p>

<p>Install jsdom and jquery.</p>

<code name="javascript">
$ npm install jsdom
$ npm install jquery
</code>

<p>Write JavaScript file.</p>

<code name="javascript">
var jsdom = require('jsdom');
var dom = new jsdom.JSDOM();
var window = dom.window;
var document = window.document;

var $ = require('jquery')(window);
console.log('version:', $.fn.jquery);

var $content = $('<p><a href="https://www.example.com/">Link</a></p>');
console.log('text:', $content.text());
console.log('html:', $content.html());
console.log('href:', $content.find('a').attr('href'));
</code>

<p>Run JavaScript file.</p>

<code name="bash">
$ node script.js
version: 3.2.1
text: Link
html: <a href="https://www.example.com/">Link</a>
href: https://www.example.com/
</code>