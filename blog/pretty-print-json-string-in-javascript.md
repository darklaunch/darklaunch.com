Pretty print a JSON string using JavaScript into an easy-to-read format with indentation and whitespace.
```javascript
var input = '{"null":null,"true":true,"false":false,"integer":1,"float":3.14,"string":"string"}';
var output = JSON.stringify(JSON.parse(input), null, 2);
```
```javascript
"{
  "null": null,
  "true": true,
  "false": false,
  "integer": 1,
  "float": 3.14,
  "string": "string"
}"
```