<p>Find html nodes using document.querySelectorAll and remove them.</p>

<code name="javascript">
var nodes = document.querySelectorAll('.someSelector');
nodes.forEach(node => node.parentNode.removeChild(node));
</code>