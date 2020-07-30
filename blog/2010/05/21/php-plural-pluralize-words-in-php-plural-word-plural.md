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
https://www.darklaunch.com/2010/05/21/php-plural-pluralize-words-in-php-plural-word-plural