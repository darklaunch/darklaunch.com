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
    if(is_array($assoc) &amp;&amp; count($assoc)&gt;0)
    {
        foreach ($assoc as $tk =&gt; $tv) 
        {
            $return[] = $tk . $inglue . $tv;
        }
        return implode(';', $return);
    }
    return false;
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
        $return = [];
        $assoc     = explode($outdelimiter, $assoc);
        
        foreach ($assoc as $ts) {
            list($key, $value) = explode($indelimiter, $ts);
            $return[$key] = $value;
        }
     
        return $return;
    }

            </div>
        </div>
    </li>
</ol>
