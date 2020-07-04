Find html nodes using document.querySelectorAll and remove them.

```javascript
var nodes = document.querySelectorAll('.someSelector');
nodes.forEach(node => node.parentNode.removeChild(node));
```