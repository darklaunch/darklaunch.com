Fix php error Cannot use object of type DOMNodeList as array. Use ->item() instead of array access.
```php
<?php
$doc = new DOMDocument();
@$doc->loadHTML($html);
$xpath = new DOMXpath($doc);

$nodes = $xpath->query('//path/to/something');

// Instead of this:
$var1 = $nodes['0'];
$var2 = $nodes['1'];
$var3 = $nodes['2'];

// Use this:
$var1 = $nodes->item(0);
$var2 = $nodes->item(1);
$var3 = $nodes->item(2);
```