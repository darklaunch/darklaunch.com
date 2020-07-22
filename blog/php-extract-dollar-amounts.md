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

`array(2) {
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
`