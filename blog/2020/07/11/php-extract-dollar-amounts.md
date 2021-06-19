# PHP extract dollar amounts

Extract dollar amounts using PHP.

Input file:

```
New statement balance: $24.99
New statement balance: $99
New statement balance: $100.20
New statement balance: $730.59
New statement balance: $1,067.94
```

```php
<?php
$input = file_get_contents('input.txt');
preg_match_all('/(\$?\d{1,3}(?:,?\d{3})*(?:\.\d{2})?)/', $input, $matches);
var_dump($matches);
```

Output:

```
array(2) {
  [0]=>
  array(5) {
    [0]=>
    string(6) "$24.99"
    [1]=>
    string(3) "$99"
    [2]=>
    string(7) "$100.20"
    [3]=>
    string(7) "$730.59"
    [4]=>
    string(9) "$1,067.94"
  }
  [1]=>
  array(5) {
    [0]=>
    string(6) "$24.99"
    [1]=>
    string(3) "$99"
    [2]=>
    string(7) "$100.20"
    [3]=>
    string(7) "$730.59"
    [4]=>
    string(9) "$1,067.94"
  }
}
```

Regex explained:

```php
$DOLLAR_AMOUNT_REGEX =
    '(' .                // begin capture group
        '\$?' .          // dollar sign, optional
        '\d{1,3}'.       // 1-3 digits

        '(' .            // begin group
            '?:' .       // non-capturing group
            ',?' .       // comma, optional
            '\d{3}' .    // 3 digits
        ')' .            // end group
        '*' .            // group repeats any number of times

        '(' .            // begin group
            '?:' .       // non-capturing group
            '\.' .       // period
            '\d{2}' .    // 2 digits
        ')' .            // end group
        '?' .            // group is optional

    ')' .                // end capture group
    '';
```

---

Posted Jul 11, 2020.

https://www.darklaunch.com/2020/07/11/php-extract-dollar-amounts.html