```php
define('CR', "\r");          // Carriage Return: Mac
define('LF', "\n");          // Line Feed: Unix
define('CRLF', "\r\n");      // Carriage Return and Line Feed: Windows
define('BR', '&lt;br />' . LF); // HTML Break
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

<ol>
    <li>
        <div>
            anonymous &ndash; Oct 7, 2010
            <div>
                <p>CR: Mac</p><p>LF: Unix</p><p>CRLF: Windows</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 3, 2011
            <div>
                <p>LF:&nbsp;&nbsp;&nbsp;&nbsp;Line Feed, U+000A</p><p> VT:&nbsp;&nbsp;&nbsp;&nbsp;Vertical Tab, U+000B</p><p> FF:&nbsp;&nbsp;&nbsp;&nbsp;Form Feed, U+000C</p><p> CR:&nbsp;&nbsp;&nbsp;&nbsp;Carriage Return, U+000D</p><p> CR+LF: CR (U+000D) followed by LF (U+000A)</p><p> NEL:   Next Line, U+0085</p><p> LS:&nbsp;&nbsp;&nbsp;&nbsp;Line Separator, U+2028</p><p> PS:&nbsp;&nbsp;&nbsp;&nbsp;Paragraph Separator, U+2029</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 16, 2012
            <div>
                <p>Thank you</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 1, 2013
            <div>
                <p>I had a problem reading text from a mysqul database in order to create a shell script... But the scrip came out with line break in different format and could not be executed properly. So I use your script to convert text from database... AND IT WORKS fine. Thanks a lot</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 24, 2013
            <div>
                <p>Nice one .)</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 24, 2014
            <div>
                <p>Use "/\n{3,}/" instead of "/\n{2,}/" for the regex. It is pointless to replace "\n\n" with "\n\n".</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 23, 2019
            <div>
                <p>$s = str_replace("\r\n", "\n", $s);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$s = str_replace("\r", "\n", $s);</p><p>???</p><p></p><p>&nbsp;&nbsp;&nbsp;&nbsp;$s = str_replace(["\r\n", "\n"], "\n", $s);</p>
            </div>
        </div>
    </li>
</ol>
