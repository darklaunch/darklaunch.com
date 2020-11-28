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

---

Posted May 30, 2009.

https://www.darklaunch.com/2009/05/30/php-implode-with-key-implode-array-with-key-and-value.html

---

8 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Mar 24, 2010
            <div>
                <p>This is great!!!!! expecially if you need to store serialized multidimensional array into database!</p><p></p><p>thank's!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
                <p>why there is $return = ''; as very first line of the function ..... this code will never give yu the result....but still i Appriciate your work helped me a lot thanx</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
                <p>for storing into database look at serialize(), base64encode()</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
                <p>this code will give a result; "$return" is not the same as "return"</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 10, 2013
            <div>
                <p>What about:</p><p>function implode_with_key($assoc, $inglue = ':')</p><p>{</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if(is_array($assoc) &amp;&amp; count($assoc)&gt;0)</p><p>&nbsp;&nbsp;&nbsp;&nbsp;{</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;foreach ($assoc as $tk =&gt; $tv) </p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return[] = $tk . $inglue . $tv;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return implode(';', $return);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;return false;</p><p>}</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 7, 2013
            <div>
                <p>This is exactly what I was looking for! Thanks for sharing.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 7, 2013
            <div>
                <p>This is exactly what I was looking for! Thanks for sharing.</p><p>I changed the inglue from , to =&gt;. Makes more sense to me.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 12, 2016
            <div>
                <p>function explode_with_key($assoc, $indelimiter = '=', $outdelimiter = '|') {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return = [];</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$assoc &nbsp;&nbsp;&nbsp;&nbsp;= explode($outdelimiter, $assoc);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;foreach ($assoc as $ts) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;list($key, $value) = explode($indelimiter, $ts);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return[$key] = $value;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp; </p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return $return;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p>
            </div>
        </div>
    </li>
</ol>
