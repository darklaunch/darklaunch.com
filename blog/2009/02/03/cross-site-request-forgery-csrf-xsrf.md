CSRF ("sea-surf").

Example:
```html
/* from http://malicious-site.com/index.php */
<html>
	<body>
		<img alt="you have just been signed out" src="http://example.com/signout" />
	</body>
</html>
```

What's going on?
You just requested an image and it signed you out of example.com.

How does it work?
You visit a malicious site that has the <img /> tag. Technically you are requesting the sign out page and provide the proper authentication (that is, without crossing domains). Because you requested the page, you have been signed out.

More
The <img /> tag is one example. A form and data can be submitted. An iframe can be requested (&lt;iframe src="http://example.com/signout">&lt;/iframe>).

---

Posted Feb 3, 2009.

https://www.darklaunch.com/2009/02/03/cross-site-request-forgery-csrf-xsrf.html