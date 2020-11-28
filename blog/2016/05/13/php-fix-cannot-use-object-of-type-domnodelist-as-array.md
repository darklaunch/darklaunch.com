Fix php error Cannot use object of type DOMNodeList as array. Use `->item()` instead of array access.

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

---

Posted May 13, 2016.

https://www.darklaunch.com/2016/05/13/php-fix-cannot-use-object-of-type-domnodelist-as-array.html

---

3 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Apr 2, 2018
            <div>
                <p>Very helpful!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 17, 2018
            <div>
                <p>Very helpful! too</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 17, 2018
            <div>
                <p>Very helpful! too too</p>
            </div>
        </div>
    </li>
</ol>
