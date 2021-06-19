# PHP Normalize Newlines/Line Endings; CRLF; CR; LF; UNIX, Windows, Mac

```php
define('CR', "\r");          // Carriage Return: Mac
define('LF', "\n");          // Line Feed: Unix
define('CRLF', "\r\n");      // Carriage Return and Line Feed: Windows
define('BR', '<br />' . LF); // HTML Break
```

```php
// Normalize line endings.
function normalize($s) {
    // Convert all line-endings to UNIX format.
    $s = str_replace(array("\r\n", "\r", "\n"), "\n", $s);

    // Don't allow out-of-control blank lines.
    $s = preg_replace("/\n{3,}/", "\n\n", $s);
    return $s;
}
```

---

Posted May 6, 2009.

https://www.darklaunch.com/2009/05/06/php-normalize-newlines-line-endings-crlf-cr-lf-unix-windows-mac.html

---

7 comments

<ol><li><div>

anonymous &ndash; Oct 7, 2010<div>

CR: Mac
LF: Unix
CRLF: Windows

</div></div></li><li><div>

anonymous &ndash; Nov 3, 2011<div>

LF:    Line Feed, U+000A
 VT:    Vertical Tab, U+000B
 FF:    Form Feed, U+000C
 CR:    Carriage Return, U+000D
 CR+LF: CR (U+000D) followed by LF (U+000A)
 NEL:   Next Line, U+0085
 LS:    Line Separator, U+2028
 PS:    Paragraph Separator, U+2029

</div></div></li><li><div>

anonymous &ndash; Nov 16, 2012<div>

Thank you

</div></div></li><li><div>

anonymous &ndash; Sep 1, 2013<div>

I had a problem reading text from a mysqul database in order to create a shell script... But the scrip came out with line break in different format and could not be executed properly. So I use your script to convert text from database... AND IT WORKS fine. Thanks a lot

</div></div></li><li><div>

anonymous &ndash; Oct 24, 2013<div>

Nice one .)

</div></div></li><li><div>

anonymous &ndash; Jul 24, 2014<div>

Use "/\n{3,}/" instead of "/\n{2,}/" for the regex. It is pointless to replace "\n\n" with "\n\n".

</div></div></li><li><div>

anonymous &ndash; Jul 23, 2019<div>

$s = str_replace("\r\n", "\n", $s);
    $s = str_replace("\r", "\n", $s);
???

    $s = str_replace(["\r\n", "\n"], "\n", $s);

</div></div></li></ol>