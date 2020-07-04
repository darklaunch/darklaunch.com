A relative URL without a scheme is perfectly valid.
```javascript
<script src="//www.example.com/script.js"></script>
```
```html
<link href="//www.example.com/style.css" rel="stylesheet" type="text/css" />
```
```html
<img alt="" src="//www.example.com/image.png" />
```
```
https://www.example.com:8080/some/resource?key=value#hash
\___/   \_____________/ \__/ \___________/ \_______/ \__/
  |            |         |         |           |      |
scheme        host      port      path       query   fragment
```