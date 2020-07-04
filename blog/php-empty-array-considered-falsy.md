Empty arrays in PHP are falsy.
```sh
$ php -r 'var_dump((bool)array());'
bool(false)
```
https://secure.php.net/manual/en/types.comparisons.php