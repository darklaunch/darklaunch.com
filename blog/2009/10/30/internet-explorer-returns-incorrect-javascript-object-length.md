# Internet Explorer Returns Incorrect JavaScript Object Length

Internet Explorer will incorrectly give an object length off by one if the object contains a trailing comma. In the example below, the alerts return 5 and 6, respectively.
```html
<!doctype html>
<html>
<head>
	<meta http-equiv="content-type" content="text/html; charset=UTF-8">
	<title></title>
</head>
<body>
	<script type="text/javascript">
	alert(
		[
			'a',
			'b',
			'c',
			'd',
			'e'
		].length
	);
	alert(
		[
			'a',
			'b',
			'c',
			'd',
			'e',
		].length
	);
	</script>
</body>
</html>
```

---

Posted Oct 30, 2009.

https://www.darklaunch.com/2009/10/30/internet-explorer-returns-incorrect-javascript-object-length.html