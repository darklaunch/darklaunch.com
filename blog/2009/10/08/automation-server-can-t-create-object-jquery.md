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
	&lt;script type="text/javascript">
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