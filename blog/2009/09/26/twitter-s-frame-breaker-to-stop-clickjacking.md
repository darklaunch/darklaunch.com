Twitter uses a frame breaker to help mitigate clickjacking. Interesting implementation:
```javascript
if (window.top !== window.self) {
	document.write = '';
	window.top.location = window.self.location;
	setTimeout(function() {
		document.body.innerHTML = '';
	},
	1);
	window.self.onload = function(evt) {
		document.body.innerHTML = '';
	};
}
```
```
if top window is not this window{
	render the page starting here
	refresh the page making me the top window to break out of any frames
	remove page content (html including graphics, buttons, etc)
	when window loads, again remove page content
}
```

NOTE: i think they meant document.write('');

---

Posted Sep 26, 2009.

https://www.darklaunch.com/2009/09/26/twitter-s-frame-breaker-to-stop-clickjacking.html