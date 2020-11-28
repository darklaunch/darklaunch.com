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

---

Posted Aug 7, 2009.

https://www.darklaunch.com/2009/08/07/base58-encode-and-decode-using-php-with-example-base58-encode-base58-decode.html

---

7 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Jan 26, 2012
            <div>

base58_encode('74') =&gt; 2h

I do not see how this can be true. Why neglect the "1"?

base58_encode('74') should be  1h, no?

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 4, 2013
            <div>

```
BASE2_ALPHABET = '01'
BASE16_ALPHABET = '0123456789ABCDEF'
BASE56_ALPHABET = '23456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnpqrstuvwxyz'
BASE36_ALPHABET = '0123456789abcdefghijklmnopqrstuvwxyz'
BASE62_ALPHABET = '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'
BASE64_ALPHABET = BASE62_ALPHABET + '-_'
```

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 23, 2013
            <div>

I think it is more common with base58 to encode with this alphabet (note that capitals are first): 

123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 14, 2014
            <div>

```
BASE2_ALPHABET = '01'
BASE16_ALPHABET = '0123456789ABCDEF'
BASE56_ALPHABET = '23456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnpqrstuvwxyz'
BASE36_ALPHABET = '0123456789abcdefghijklmnopqrstuvwxyz'
BASE62_ALPHABET = '0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'
BASE64_ALPHABET = BASE62_ALPHABET + '-_'
```

from
<a href="https://github.com/django/django/blob/master/django/utils/baseconv.py">https://github.com/django/django/blob/master/django/utils/baseconv.py</a>

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 6, 2016
            <div>

For Bitcoin:

```
/** All alphanumeric characters except for "0", "I", "O", and "l" */
static const char* pszBase58 = "123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz";
```

from <a href="https://github.com/bitcoin/bitcoin/blob/HEAD/src/base58.cpp">https://github.com/bitcoin/bitcoin/blob/HEAD/src/base58.cpp</a>

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 12, 2017
            <div>

i want as bash!!!!

            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 12, 2018
            <div>

Regarding first comment:
_________________
base58_encode('74') =&gt; 2h
I do not see how this can be true. Why neglect the "1"?
base58_encode('74') should be  1h, no?
_________________

I tried very hard wrapping my head around this one as I couldn't get WHY it was not working that way.
Up to the point that I was almost reinventing the wheel by writing my own routine with the same alphabet, and is was then and there that I finally realized: I made a parallel with the alphabet "0123456789"... when you're counting up to "9", you don't really expect to have "00" next, rather you have "10", as "9" is actually "09". Well, base58 has no "0", so guess what, it's "1" that takes the value of 0 in that alphabet. BAM everything makes sense now.
Thanks brain.

            </div>
        </div>
    </li>
</ol>
