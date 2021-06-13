"Automation server can't create object" fixed:

Run your script with jquery-1.3.2.js (not compressed version) and the error is occurring on line 3382.

Lines 3381, 3382, 3383:
```javascript
xhr:function(){
	return window.ActiveXObject ? new ActiveXObject("Microsoft.XMLHTTP") : new XMLHttpRequest();
},
```

Replace the xhr function with:
```javascript
xhr:function(){
	if (window.XMLHttpRequest) {
		return new XMLHttpRequest();
	}
	else if (window.ActiveXObject) {
		try {
			return new ActiveXObject("Microsoft.XMLHTTP");
		}
		catch(e) {
			try {
				return new ActiveXObject("Msxml2.XMLHTTP");
			}
			catch(e) {
				return false;
			}
		}
	}
},
```

The following code reproduces the error message in Internet Explorer 8:
```html
<!doctype html>
<html>
<head>
	<meta http-equiv="content-type" content="text/html; charset=UTF-8">
	<title></title>
	<script type="text/javascript" src="http://jqueryjs.googlecode.com/files/jquery-1.3.2.js"></script>
</head>
<body>
	<script type="text/javascript">
	$.ajax({
		type: 'GET',
		url: 'http://127.0.0.1/'
	});
	</script>
</body>
</html>
```

<img alt="image" src="/img/uploads/2009-10/Iq0Wu.png" />

---

Posted Oct 8, 2009.

https://www.darklaunch.com/2009/10/08/automation-server-can-t-create-object-jquery.html

---

2 comments

<ol><li><div>

anonymous &ndash; Jun 24, 2010<div>

Note, while this is an old post, it came up high on a Google search. jQuery has addressed this similarly, but with refinements, in later code (sample below from 1.4.2, released a year later):

```
xhr: window.XMLHttpRequest && (window.location.protocol !== "file:" || !window.ActiveXObject) ?
  function() {
    return new window.XMLHttpRequest();
  } :
    function() {
      try {
    return new window.ActiveXObject("Microsoft.XMLHTTP");
      } catch(e) {}
}, ...
```

The code's internal comments indicate that this is a failing in IE7+ as a result of a Microsoft oversight. While I would normally upgrade jQuery, the correction above tries something jQuery does not (and visitor's mileage may vary), so I'm posting an update as a courtesy (and to darklaunch, thanks for posting the cause).

One final thing -- it is possible to work around this error at the client side (which is "caused" by IE policy settings) by explicitly adding the site into the Trusted Sites zone (I applied this to *machine* policy zones, so that all users of IE saw the update...regardless of who's logged in / created after the policy is implemented).

</div></div></li><li><div>

anonymous &ndash; Oct 24, 2010<div>

thanks  -- vv helpful

</div></div></li></ol>