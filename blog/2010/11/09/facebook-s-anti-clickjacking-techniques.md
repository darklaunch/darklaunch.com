Facebook uses a frame breaker to help mitigate clickjacking: `X-Frame-Options` with "deny". They send off analytics in the process.

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

They also specify `X-Frame-Options` in a meta tag. The value deny is to block the content from rendering if it is contained in a frame.

```
<noscript><meta http-equiv="X-Frame-Options" content="deny"/></noscript>
```

---

Posted Nov 9, 2010.

https://www.darklaunch.com/2010/11/09/facebook-s-anti-clickjacking-techniques.html

---

2 comments

<ol>
    <li>
        <div>
            anonymous &ndash; May 22, 2011
            <div>
if I had full access to the dom how could I disable this using a script of my own? I ask because im trying to create automation software in Titanium but I have to use iframes. with titanium I have full access to cross site dom but this frame breaker is stopping me from doing anything because it takes over my app window.
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 23, 2011
            <div>
take a look at window.onbeforeunload and sending a 204 header
            </div>
        </div>
    </li>
</ol>
