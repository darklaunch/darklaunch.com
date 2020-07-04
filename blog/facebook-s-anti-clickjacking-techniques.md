Facebook uses a frame breaker to help mitigate clickjacking: X-Frame-Options with "deny". They send off analytics in the process.
```javascript
&lt;script type="text/javascript">
/* <![CDATA[ */
if (top != self) {
    try {
        if (parent != top) {
            throw 1;
        }
    } catch (e) {
        setTimeout(function() {
            var fb_cj_img = new Image();
            fb_cj_img.src = "http:\/\/error.facebook.com\/common\/scribe_endpoint.php?c=si_clickjacking&m&t=";
        }, 5000);
        window.document.write("<style>body * { display:none !important; }<\/style><a href=\"#\" onclick=\"top.location.href=window.location.href\" style=\"display: block !important; padding: 10px\"><i class=\"img spritemap_3e9q9m sx_5eabfc\" style=\"display:block !important\"><\/i>Go to Facebook.com<\/a>");
    }
}
/* ]]> */
&lt;/script>
```
They also specify X-Frame-Options in a meta tag. The value deny is to block the content from rendering if it is contained in a frame.
```
<noscript><meta http-equiv="X-Frame-Options" content="deny"/></noscript>
```