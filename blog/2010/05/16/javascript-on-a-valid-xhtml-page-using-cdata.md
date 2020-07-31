Best option:
```javascript
&lt;script type="text/javascript">
/* <![CDATA[ */
var someScriptHere;
/* ]]> */
</script>
```
Can be written on one line:
```javascript
&lt;script type="text/javascript">/* <![CDATA[ */var someScriptHere;/* ]]> */</script>
```
Further Testing:
```php
<?php
$javascript =
	'var foo = 1, bar = 2;' .
	'foo && bar;' .
	'alert("horray!");' .
	'';

// character "&amp;" is the first character of a delimiter but occurred as data
// unescaped ampersand error
// xmlParseEntityRef: no name
// multiple lines
// alert works
$script_1A =
	'&lt;script type="text/javascript">' . "\n" .
		$javascript . "\n" .
	'</script>' . "\n" .
	'';
	
// character "&amp;" is the first character of a delimiter but occurred as data
// unescaped ampersand error
// xmlParseEntityRef: no name
// one line
// alert works
$script_1B =
	'&lt;script type="text/javascript">' .
		$javascript .
	'</script>' .
	'';
	
// Valid XHTML 1.0 Strict
// multiple lines
// alert works
$script_2A =
	'&lt;script type="text/javascript">' . "\n" .
	'//<![CDATA[' . "\n" .
		$javascript . "\n" .
	'//]]>' . "\n" .
	'</script>' . "\n" .
	'';
	
// Valid XHTML 1.0 Strict
// one line
// alert does not work (commented out)
$script_2B =
	'&lt;script type="text/javascript">' .
	'//<![CDATA[' .
		$javascript .
	'//]]>' .
	'</script>' .
	'';
	
// Valid XHTML 1.0 Strict
// multiple lines
// alert works
$script_3A =
	'&lt;script type="text/javascript">' . "\n" .
	'/* <![CDATA[ */' . "\n" .
		$javascript . "\n" .
	'/* ]]> */' . "\n" .
	'</script>' . "\n" .
	'';
	
// BEST OPTION
// Valid XHTML 1.0 Strict
// alert works
// one line
$script_3B =
	'&lt;script type="text/javascript">' .
	'/* <![CDATA[ */' .
		$javascript .
	'/* ]]> */' .
	'</script>' .
	'';

echo
	'<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">' .
	'<html xmlns="http://www.w3.org/1999/xhtml">' .
		'<head>' .
			'<meta http-equiv="content-type" content="text/html; charset=UTF-8" />' .
			'<title>page title</title>' .
		'</head>' .
		'<body>' .
/*
			$script_1A .
			$script_1B .
			$script_2A .
			$script_2B .
			$script_3A .
*/
			$script_3B .
/*
*/
		'</body>' .
	'</html>' .
	'';
```

NOTE: HTML5 doesn't need CDATA tags to validate. The following successfully validates:
```php
echo
	'<!doctype html>' .
	'<html>' .
		'<head>' .
			'<meta http-equiv="content-type" content="text/html; charset=UTF-8" />' .
			'<title>page title</title>' .
		'</head>' .
		'<body>' .
			$script_1A .
			$script_1B .
			$script_2A .
			$script_2B .
			$script_3A .
			$script_3B .
		'</body>' .
	'</html>' .
	'';
```

---


Posted May 16, 2010.
https://www.darklaunch.com/2010/05/16/javascript-on-a-valid-xhtml-page-using-cdata.html