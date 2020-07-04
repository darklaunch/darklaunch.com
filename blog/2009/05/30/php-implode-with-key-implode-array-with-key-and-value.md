```php
function implode_with_key($assoc, $inglue = '>', $outglue = ',') {
    $return = '';

    foreach ($assoc as $tk => $tv) {
        $return .= $outglue . $tk . $inglue . $tv;
    }

    return substr($return, strlen($outglue));
}
```

See also <a href="http://www.php.net/manual/en/function.http-build-query.php">http_build_query()</a>.