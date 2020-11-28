> Base 36 is the most compact case-insensitive alphanumeric numeral system using ASCII characters.
```php
function base36_encode($base10) {
    return base_convert($base10, 10, 36);
}

function base36_decode($base36) {
    return base_convert($base36, 36, 10);
}
```

```php
header('Content-Type: text/plain');
$array = array(
    // base10 => base36
    '1' => '1',
    '10' => 'A',
    '100' => '2S',
    '1000' => 'RS',
    '10000' => '7PS',
    '100000' => '255S',
    '1000000' => 'LFLS',
    '1000000000' => 'GJDGXS',
    '1000000000000' => 'CRE66I9S',
);

foreach ($array as $base10 => $base36) {
    echo "base36_encode('" . $base10 . "') => " .
        base36_encode($base10) . "\n";
}

echo "\n";

foreach ($array as $base10 => $base36) {
    echo "base36_decode('" . $base36 . "') => " .
        base36_decode($base36) . "\n";
}

echo "\n";

foreach ($array as $base10 => $base36) {
    echo "base36_decode('" . strtolower($base36) . "') => " .
        base36_decode(strtolower($base36)) . "\n";
}
```

```
base36_encode('1') => 1
base36_encode('10') => a
base36_encode('100') => 2s
base36_encode('1000') => rs
base36_encode('10000') => 7ps
base36_encode('100000') => 255s
base36_encode('1000000') => lfls
base36_encode('1000000000') => gjdgxs
base36_encode('1000000000000') => cre66i9s

base36_decode('1') => 1
base36_decode('A') => 10
base36_decode('2S') => 100
base36_decode('RS') => 1000
base36_decode('7PS') => 10000
base36_decode('255S') => 100000
base36_decode('LFLS') => 1000000
base36_decode('GJDGXS') => 1000000000
base36_decode('CRE66I9S') => 1000000000000

base36_decode('1') => 1
base36_decode('a') => 10
base36_decode('2s') => 100
base36_decode('rs') => 1000
base36_decode('7ps') => 10000
base36_decode('255s') => 100000
base36_decode('lfls') => 1000000
base36_decode('gjdgxs') => 1000000000
base36_decode('cre66i9s') => 1000000000000
```

---

Posted Jul 31, 2009.

https://www.darklaunch.com/2009/07/31/base36-encode-and-decode-using-php-with-example-base36-encode-base36-decode.html

---

5 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Jul 19, 2011
            <div>

nice

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 5, 2012
            <div>

thanks a lot :)

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 13, 2012
            <div>

nice

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 3, 2015
            <div>

+1! Thanks!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 15, 2019
            <div>

Yes, of course.
Thanks a lot.

            </div>
        </div>
    </li>
</ol>
