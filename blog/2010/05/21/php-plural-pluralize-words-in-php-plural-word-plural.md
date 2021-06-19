# PHP Plural; Pluralize Words in PHP; Plural Word, plural()

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

<ol><li><div>

anonymous &ndash; Jul 7, 2014<div>

Child plural is children not childs.

Party plural is Parties not Partys.

</div></div></li><li><div>

anonymous &ndash; Jul 7, 2014<div>

for ($i = 0; $i <= 3; $i++) {
    echo $i . ' ' . plural($i, 'child', 'children') . "\n";
}

0 children
1 child
2 children
3 children

</div></div></li></ol>