<code name="js">
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
</code>