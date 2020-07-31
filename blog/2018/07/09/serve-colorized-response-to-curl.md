Use an ANSI escape sequence to display color in the curl output.

<img alt="" src="/img/uploads/2018-07/colorized-curl-http-response.png" />

```
The SGR control sequence: CSI + number + m
The CSI escape sequence: ESC [
The ASCII escape character octal: \033
```

Starting with the the SGR control sequence to colorize the html response:
```
CSI + number + m
```

Replace CSI with the CSI escape sequence:
```
ESC [ + number + m
```

Replace ESC with the escape character octal:
```
\033[ + number + m
```

Using the green foreground color code (32) and the reset code (0), construct a message in green.

```
\033[ + 32 + m +
text +
\033[ + 0 + m
```

```php
<?php
echo "\033[32m" . 'Success!' . "\033[0m\n";
exit;
```

<img alt="" src="/img/uploads/2018-07/colorized-curl-http-success-response.png" />

Use the colorize function like this:

```php
echo colorize('Success!', 'green_fg') . "\n";
echo colorize('Warning!', 'yellow_fg;underline') . "\n";
```

```php
<?php
function colorize($str, $attributes) {
    $ANSI_ESCAPE_CODES = array(
        'reset'      => 0,
        'bold'       => 1,
        'italic'     => 3,
        'underline'  => 4,
        'blink'      => 5,
        'reverse'    => 7,

        // Foreground colors.
        'black_fg'   => 30,
        'red_fg'     => 31,
        'green_fg'   => 32,
        'yellow_fg'  => 33,
        'blue_fg'    => 34,
        'magenta_fg' => 35,
        'cyan_fg'    => 36,
        'white_fg'   => 37,

        // Background colors.
        'black_bg'   => 40,
        'red_bg'     => 41,
        'green_bg'   => 42,
        'yellow_bg'  => 43,
        'blue_bg'    => 44,
        'magenta_bg' => 45,
        'cyan_bg'    => 46,
        'white_bg'   => 47,
    );

    $ansi = '';
    foreach (preg_split('/(,|;|\|)/', $attributes) as $attribute) {
        $ansi .= "\033[" . $ANSI_ESCAPE_CODES[$attribute] . 'm';
    }
    $ansi .= $str . "\033[" . $ANSI_ESCAPE_CODES['reset'] . 'm';
    return $ansi;
}
```

---

Posted Jul 9, 2018.

https://www.darklaunch.com/2018/07/09/serve-colorized-response-to-curl.html