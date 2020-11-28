```php
function plural($count, $singular, $plural = 's') {
    if ($plural === 's') {
        $plural = $singular . $plural;
    }
    return ($count == 1 ? $singular : $plural);
}
```
Example:
```php
$amount = 5;
echo 'And then I found ' . $amount . ' ' . plural($amount, 'dollar') . "\n";

$count = rand(1, 2);
echo 'Roll the ' . plural($count, 'die', 'dice') . "\n";
```

Output:
```
And then I found 5 dollars
Roll the die
```

---

Posted May 21, 2010.

https://www.darklaunch.com/2010/05/21/php-plural-pluralize-words-in-php-plural-word-plural.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Jul 7, 2014
            <div>
                <p>Child plural is children not childs.</p><p></p><p>Party plural is Parties not Partys.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 7, 2014
            <div>
                <p>for ($i = 0; $i &lt;= 3; $i++) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;echo $i . ' ' . plural($i, 'child', 'children') . "\n";</p><p>}</p><p></p><p>0 children</p><p>1 child</p><p>2 children</p><p>3 children</p>
            </div>
        </div>
    </li>
</ol>
