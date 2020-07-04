Use php to split a string using multiple characters like pipe, comma, semicolon, etc.
```php
<?php
$input = 'a,b|c;d';
$parts = preg_split('/(,|;|\|)/', $input);
var_dump($parts);
```
```bash
$ php split.php
array(4) {
  [0]=>
  string(1) "a"
  [1]=>
  string(1) "b"
  [2]=>
  string(1) "c"
  [3]=>
  string(1) "d"
}
```