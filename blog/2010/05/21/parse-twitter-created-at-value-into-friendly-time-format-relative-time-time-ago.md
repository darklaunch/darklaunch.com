```js
// from http://widgets.twimg.com/j/1/widget.js
var K = function () {
	var a = navigator.userAgent;
	return {
		ie: a.match(/MSIE\s([^;]*)/)
	}
}();

var H = function (a) {
	var b = new Date();
	var c = new Date(a);
	if (K.ie) {
		c = Date.parse(a.replace(/( \+)/, ' UTC$1'))
	}
	var d = b - c;
	var e = 1000,
		minute = e * 60,
		hour = minute * 60,
		day = hour * 24,
		week = day * 7;
	if (isNaN(d) || d < 0) {
		return ""
	}
	if (d < e * 7) {
		return "right now"
	}
	if (d < minute) {
		return Math.floor(d / e) + " seconds ago"
	}
	if (d < minute * 2) {
		return "about 1 minute ago"
	}
	if (d < hour) {
		return Math.floor(d / minute) + " minutes ago"
	}
	if (d < hour * 2) {
		return "about 1 hour ago"
	}
	if (d < day) {
		return Math.floor(d / hour) + " hours ago"
	}
	if (d > day && d < day * 2) {
		return "yesterday"
	}
	if (d < day * 365) {
		return Math.floor(d / day) + " days ago"
	} else {
		return "over a year ago"
	}
};

console.log(H("Wed, 08 Apr 2009 19:22:10 +0000"));
console.log(H("Thu, 20 May 2010 19:22:10 +0000"));
```

---

Posted May 21, 2010.

https://www.darklaunch.com/2010/05/21/parse-twitter-created-at-value-into-friendly-time-format-relative-time-time-ago.html

---

12 comments

<ol>
    <li>
        <div>
            anonymous &ndash; May 25, 2010
            <div>
                <p>Thanks a bunch for this!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 10, 2010
            <div>
                <p>Thank you very much</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 13, 2010
            <div>
                <p>Here's the PHP version:</p><p></p><p>function ago($a) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$b = strtotime("now"); </p><p>&nbsp;&nbsp;&nbsp;&nbsp;$c = strtotime($a);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$d = $b - $c;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$minute = 60;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$hour = $minute * 60;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$day = $hour * 24;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;$week = $day * 7;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if(is_numeric($d) &amp;&amp; $d &gt; 0) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; 3) return "right now";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $minute) return floor($d) . " seconds ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $minute * 2) return "about 1 minute ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $hour) return floor($d / $minute) . " minutes ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $hour * 2) return "about 1 hour ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $day) return floor($d / $hour) . " hours ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &gt; $day &amp;&amp; $d &lt; $day * 2) return "yesterday";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if($d &lt; $day * 365) return floor($d / $day) . " days ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "over a year ago";</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>}</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 16, 2010
            <div>
                <p>Sorry Im not sure exactly how to use this?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Nov 16, 2010
            <div>
                <p>to use:</p><p>created_at = "Wed, 08 Apr 2009 19:22:10 +0000";</p><p>alert(H(created_at));</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 22, 2011
            <div>
                <p>thank u sir</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Oct 1, 2011
            <div>
                <p>Thank you!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 15, 2012
            <div>
                <p>Gracias!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 16, 2012
            <div>
                <p>Compiled JavaScript Code has been changed:</p><p></p><p>var X = function () {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;var Z = navigator.userAgent;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;return {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ie: Z.match(/MSIE\s([^;]*)/)</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>}();</p><p></p><p>var I = function (f) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;var h = new Date();</p><p>&nbsp;&nbsp;&nbsp;&nbsp;var d = new Date(f);</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (X.ie) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;d = Date.parse(f.replace(/( \+)/, " UTC$1"))</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;var g = h - d;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;var a = 1000,</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b = a * 60,</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c = b * 60,</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;e = c * 24,</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Z = e * 7;</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (isNaN(g) || g &lt; 0) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return ""</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; a * 7) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "right now"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; b) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return Math.floor(g / a) + " seconds ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; b * 2) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "about 1 minute ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; c) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return Math.floor(g / b) + " minutes ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; c * 2) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "about 1 hour ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; e) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return Math.floor(g / c) + " hours ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &gt; e &amp;&amp; g &lt; e * 2) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "yesterday"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>&nbsp;&nbsp;&nbsp;&nbsp;if (g &lt; e * 365) {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return Math.floor(g / e) + " days ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;} else {</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return "over a year ago"</p><p>&nbsp;&nbsp;&nbsp;&nbsp;}</p><p>};</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 19, 2012
            <div>
                <p>Last work well in explorer thanks!!!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jul 20, 2012
            <div>
                <p>Thank you!!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 30, 2013
            <div>
                <p>for anyone still looking for a JavaScript implementation, use can now use Twitter's twitter-cldr-js.</p><p>see the TwitterCldr.TimespanFormatter / Relative Dates and Times.</p><p><a href="https://github.com/twitter/twitter-cldr-js">https://github.com/twitter/twitter-cldr-js</a></p>
            </div>
        </div>
    </li>
</ol>
