Find html nodes using document.querySelectorAll and remove them.

```javascript
var nodes = document.querySelectorAll('.someSelector');
nodes.forEach(node => node.parentNode.removeChild(node));
```

---

Posted Feb 13, 2019.
https://www.darklaunch.com/2019/02/13/remove-nodes-fetched-using-document.queryselectorall