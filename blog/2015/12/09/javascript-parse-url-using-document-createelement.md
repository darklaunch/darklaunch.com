Update: Use the URL() constructor to parse urls.
https://developer.mozilla.org/en-US/docs/Web/API/URL/URL

<hr />

Parse a url into components using plain vanilla JavaScript.

```javascript
var parser = document.createElement('a');
parser.href = window.location.toString();

console.log('hash:', parser.hash);
console.log('host:', parser.host);
console.log('hostname:', parser.hostname);
console.log('href:', parser.href);
console.log('origin:', parser.origin);
console.log('password:', parser.password);
console.log('pathname:', parser.pathname);
console.log('port:', parser.port);
console.log('protocol:', parser.protocol);
console.log('search:', parser.search);
console.log('toString():', parser.toString());
console.log('username:', parser.username);
```

Example JavaScript script run with Node.js using jsdom.
```javascript
var jsdom = require('jsdom');
var dom = new jsdom.JSDOM();
var window = dom.window;
var document = window.document;

var parser = document.createElement('a');
parser.href = 'https://username:password@www.example.com:9000/path?arg=value#anchor';

console.log('hash:', parser.hash);
console.log('host:', parser.host);
console.log('hostname:', parser.hostname);
console.log('href:', parser.href);
console.log('origin:', parser.origin);
console.log('password:', parser.password);
console.log('pathname:', parser.pathname);
console.log('port:', parser.port);
console.log('protocol:', parser.protocol);
console.log('search:', parser.search);
console.log('toString():', parser.toString());
console.log('username:', parser.username);
```

```bash
$ node test.js 
hash: #anchor
host: www.example.com:9000
hostname: www.example.com
href: https://username:password@www.example.com:9000/path?arg=value#anchor
origin: https://www.example.com:9000
password: password
pathname: /path
port: 9000
protocol: https:
search: ?arg=value
toString(): https://username:password@www.example.com:9000/path?arg=value#anchor
username: username
```