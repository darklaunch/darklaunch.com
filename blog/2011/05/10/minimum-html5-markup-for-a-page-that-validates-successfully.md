Minimum HTML Markup that validates. The following is valid HTML5 markup and will validate.

```html
<!doctype html>
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
<title></title>
</head>
<body>
</body>
</html>
```

Success! "This document was successfully checked as HTML5!"

Note that you will may get the "experimental feature" warning.

See the Markup Validation Service:
https://validator.w3.org/

---

Posted May 10, 2011.

https://www.darklaunch.com/2011/05/10/minimum-html5-markup-for-a-page-that-validates-successfully.html

---

2 comments

<ol><li><div>

anonymous &ndash; Aug 10, 2011<div>

You can make it shorter: the &lt;body&gt; element isn't required in HTML5. And if your server is emitting the correct headers, the charset isn't technically required either.

</div></div></li><li><div>

anonymous &ndash; Jun 18, 2012<div>

Actually, this is the minimum:

```
&lt;!doctype html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;title&gt;&lt;/title&gt;
&lt;/head&gt;
&lt;/html&gt;
```

</div></div></li></ol>