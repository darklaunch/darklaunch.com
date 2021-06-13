To capture the function's response or output to a variable, use the following function:

```php
function get_contents($function) {
    ob_start();
    $function();
    $contents = ob_get_contents();
    ob_end_clean();

    return $contents;
}
```

To use, pass an anonymous function to `get_contents()`.

Examples:

```php
// Example: get function's response to variable.
function add($this, $that) {
    echo $this . ' + ' . $that . ' = ' . ($this + $that);
}

$example = get_contents(function() {
    add(1, 1);
});

echo $example . "\n"; // 1 + 1 = 2
```
```php
// Example 2: get function's response using return. Even if the function echos output, it can be captured to a variable.
// Compare print_r() that has a return parameter to var_dump() that has no such parameter.

$return = true;
$example2 = print_r(array('a', 'b', 'c'), $return);

// Solution: use get_contents() to capture the function's response to a variable.
$example3 = get_contents(function() {
    var_dump(array('a', 'b', 'c'));
});

echo $example3;
// array(3) {
//   [0]=>
//   string(1) "a"
//   [1]=>
//   string(1) "b"
//   [2]=>
//   string(1) "c"
// }
```

Note: Anonymous functions are available since PHP 5.3.0.

---

Posted Dec 1, 2011.

https://www.darklaunch.com/2011/12/01/php-return-function-response-to-variable-rather-than-print-or-echo-it.html

---

1 comment

<ol><li><div>

anonymous &ndash; Nov 30, 2011<div>

If you're getting `"Parse error: syntax error, unexpected T_FUNCTION"`, then use a newer version of PHP (>= PHP 5.3.0) or use `create_function()`.

</div></div></li></ol>