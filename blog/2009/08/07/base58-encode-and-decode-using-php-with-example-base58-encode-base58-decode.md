Base58 is base62 with ambiguous characters removed. These removed are 0, O, l, I for the Flickr Base58 character set.
```
Alphabet:       0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
Bitcoin Base58: 123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz
Base62:         0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
Flickr Base58:  123456789abcdefghijkmnopqrstuvwxyzABCDEFGHJKLMNPQRSTUVWXYZ
```
Alphabets aligned for comparison:
```
Alphabet:       0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
Bitcoin Base58:  123456789ABCDEFGH JKLMN PQRSTUVWXYZabcdefghijk mnopqrstuvwxyz
Base62:         0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
Flickr Base58:   123456789abcdefghijk mnopqrstuvwxyzABCDEFGH JKLMN PQRSTUVWXYZ
```
```php
function base58_encode($num) {
    $alphabet = '123456789abcdefghijkmnopqrstuvwxyzABCDEFGHJKLMNPQRSTUVWXYZ';
    $base_count = strlen($alphabet);
    $encoded = '';

    while ($num >= $base_count) {
        $div = $num / $base_count;
        $mod = ($num - ($base_count * intval($div)));
        $encoded = $alphabet[$mod] . $encoded;
        $num = intval($div);
    }

    if ($num) {
        $encoded = $alphabet[$num] . $encoded;
    }

    return $encoded;
}

function base58_decode($num) {
    $alphabet = '123456789abcdefghijkmnopqrstuvwxyzABCDEFGHJKLMNPQRSTUVWXYZ';
    $len = strlen($num);
    $decoded = 0;
    $multi = 1;

    for ($i = $len - 1; $i >= 0; $i--) {
        $decoded += $multi * strpos($alphabet, $num[$i]);
        $multi = $multi * strlen($alphabet);
    }

    return $decoded;
}
```
```php
$array =
    array(
        // base10 => base58
        '3429289555' => '6e31iZ',
        '3368' => '215',
        '74' => '2h',
        '75' => '2i',
        '94' => '2C',
        '88' => '2w',
        '195102' => 'ZZQ',
        '1253576' => '7qDo',
        '177' => '44',
        '193' => '4k',
        '195' => '4n',
    );

foreach ($array as $base10 => $base58) {
    echo 'base58_encode(\'', $base10, '\') => ' . base58_encode($base10) . "\n";
    echo 'base58_decode(\'', $base58, '\') => ' . base58_decode($base58) . "\n";
}
```
```
base58_encode('3429289555') => 6e31iZ
base58_decode('6e31iZ') => 3429289555
base58_encode('3368') => 215
base58_decode('215') => 3368
base58_encode('74') => 2h
base58_decode('2h') => 74
base58_encode('75') => 2i
base58_decode('2i') => 75
base58_encode('94') => 2C
base58_decode('2C') => 94
base58_encode('88') => 2w
base58_decode('2w') => 88
base58_encode('195102') => ZZQ
base58_decode('ZZQ') => 195102
base58_encode('1253576') => 7qDo
base58_decode('7qDo') => 1253576
base58_encode('177') => 44
base58_decode('44') => 177
base58_encode('193') => 4k
base58_decode('4k') => 193
base58_encode('195') => 4n
base58_decode('4n') => 195
```