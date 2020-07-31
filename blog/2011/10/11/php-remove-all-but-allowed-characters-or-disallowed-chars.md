The following will remove all characters but those allowed using `preg_replace()`.

```php
$input = '"Shall I compare thee to a summer\'s day?"';
$output = preg_replace('/[^A-Za-z0-9]/', ' ', $input);
echo 'input:  ' . $input . "\n";
echo 'output: ' . $output . "\n";
```

```
input:  "Shall I compare thee to a summer's day?"
output:  Shall I compare thee to a summer s day 
```

Another example which replaces the delimiter character with the at symbol.

```php
$str = preg_replace('@[^a-zA-Z0-9_:;\(\)\?\|\&=!<>+*/\%-]@', '', $str);
```

Common alternate delimiters: #, @, !

---

Posted Oct 11, 2011.

https://www.darklaunch.com/2011/10/11/php-remove-all-but-allowed-characters-or-disallowed-chars.html