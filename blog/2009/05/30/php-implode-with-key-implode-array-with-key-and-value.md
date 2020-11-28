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
This is great!!!!! expecially if you need to store serialized multidimensional array into database!

thank's!
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
why there is $return = ''; as very first line of the function ..... this code will never give yu the result....but still i Appriciate your work helped me a lot thanx
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
for storing into database look at serialize(), base64encode()
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 23, 2010
            <div>
this code will give a result; "$return" is not the same as "return"
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 10, 2013
            <div>
What about:
function implode_with_key($assoc, $inglue = ':')
{
&nbsp;&nbsp;&nbsp;&nbsp;if(is_array($assoc) &amp;&amp; count($assoc)&gt;0)
&nbsp;&nbsp;&nbsp;&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;foreach ($assoc as $tk =&gt; $tv) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return[] = $tk . $inglue . $tv;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return implode(';', $return);
&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;return false;
}
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 7, 2013
            <div>
This is exactly what I was looking for! Thanks for sharing.
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 7, 2013
            <div>
This is exactly what I was looking for! Thanks for sharing.
I changed the inglue from , to =&gt;. Makes more sense to me.
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 12, 2016
            <div>
function explode_with_key($assoc, $indelimiter = '=', $outdelimiter = '|') {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return = [];
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$assoc &nbsp;&nbsp;&nbsp;&nbsp;= explode($outdelimiter, $assoc);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;foreach ($assoc as $ts) {
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;list($key, $value) = explode($indelimiter, $ts);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$return[$key] = $value;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp; 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return $return;
&nbsp;&nbsp;&nbsp;&nbsp;}
            </div>
        </div>
    </li>
</ol>
