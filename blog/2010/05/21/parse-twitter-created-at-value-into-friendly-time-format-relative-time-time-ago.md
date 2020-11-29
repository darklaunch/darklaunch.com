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

<ol><li><div>

anonymous &ndash; May 25, 2010<div>

Thanks a bunch for this!

</div></div></li><li><div>

anonymous &ndash; Jun 10, 2010<div>

Thank you very much

</div></div></li><li><div>

anonymous &ndash; Oct 13, 2010<div>

Here's the PHP version:

function ago($a) {
        
    $b = strtotime("now"); 
    $c = strtotime($a);
    $d = $b - $c;
    $minute = 60;
    $hour = $minute * 60;
    $day = $hour * 24;
    $week = $day * 7;
        
    if(is_numeric($d) &amp;&amp; $d &gt; 0) {
        
        if($d &lt; 3) return "right now";
        if($d &lt; $minute) return floor($d) . " seconds ago";
        if($d &lt; $minute * 2) return "about 1 minute ago";
        if($d &lt; $hour) return floor($d / $minute) . " minutes ago";
        if($d &lt; $hour * 2) return "about 1 hour ago";
        if($d &lt; $day) return floor($d / $hour) . " hours ago";
        if($d &gt; $day &amp;&amp; $d &lt; $day * 2) return "yesterday";
        if($d &lt; $day * 365) return floor($d / $day) . " days ago";
        
        return "over a year ago";
    }
}

</div></div></li><li><div>

anonymous &ndash; Nov 16, 2010<div>

Sorry Im not sure exactly how to use this?

</div></div></li><li><div>

anonymous &ndash; Nov 16, 2010<div>

to use:
created_at = "Wed, 08 Apr 2009 19:22:10 +0000";
alert(H(created_at));

</div></div></li><li><div>

anonymous &ndash; Sep 22, 2011<div>

thank u sir

</div></div></li><li><div>

anonymous &ndash; Oct 1, 2011<div>

Thank you!

</div></div></li><li><div>

anonymous &ndash; May 15, 2012<div>

Gracias!

</div></div></li><li><div>

anonymous &ndash; May 16, 2012<div>

Compiled JavaScript Code has been changed:

var X = function () {
    var Z = navigator.userAgent;
    return {
        ie: Z.match(/MSIE\s([^;]*)/)
    }
}();

var I = function (f) {
    var h = new Date();
    var d = new Date(f);
    if (X.ie) {
        d = Date.parse(f.replace(/( \+)/, " UTC$1"))
    }
    var g = h - d;
    var a = 1000,
        b = a * 60,
        c = b * 60,
        e = c * 24,
        Z = e * 7;
    if (isNaN(g) || g &lt; 0) {
        return ""
    }
    if (g &lt; a * 7) {
        return "right now"
    }
    if (g &lt; b) {
        return Math.floor(g / a) + " seconds ago"
    }
    if (g &lt; b * 2) {
        return "about 1 minute ago"
    }
    if (g &lt; c) {
        return Math.floor(g / b) + " minutes ago"
    }
    if (g &lt; c * 2) {
        return "about 1 hour ago"
    }
    if (g &lt; e) {
        return Math.floor(g / c) + " hours ago"
    }
    if (g &gt; e &amp;&amp; g &lt; e * 2) {
        return "yesterday"
    }
    if (g &lt; e * 365) {
        return Math.floor(g / e) + " days ago"
    } else {
        return "over a year ago"
    }
};

</div></div></li><li><div>

anonymous &ndash; May 19, 2012<div>

Last work well in explorer thanks!!!

</div></div></li><li><div>

anonymous &ndash; Jul 20, 2012<div>

Thank you!!

</div></div></li><li><div>

anonymous &ndash; Aug 30, 2013<div>

for anyone still looking for a JavaScript implementation, use can now use Twitter's twitter-cldr-js.
see the TwitterCldr.TimespanFormatter / Relative Dates and Times.
<a href="https://github.com/twitter/twitter-cldr-js">https://github.com/twitter/twitter-cldr-js</a>

</div></div></li></ol>