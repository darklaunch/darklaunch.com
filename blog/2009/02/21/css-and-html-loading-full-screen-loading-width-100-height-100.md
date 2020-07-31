```html
<div id="splash">
    <table height="90%" width="100%">
        <tbody>
            <tr>
                <td height="100%" align="center" width="100%" valign="middle">
                    <div id="splash_loading">Loading</div>
                </td>
            </tr>
        </tbody>
    </table>
</div>
```

```css
#splash{
    cursor:wait;
    height:100%;
    left:0;
    position:absolute;
    top:0;
    width:100%;
}
#splash .loaded{
    display:none;
}
#splash_loading{
    background-image:url(loading.gif);
    cursor:wait;
    height:80px;
    width:200px;
}
```

---

Posted Feb 21, 2009.

https://www.darklaunch.com/2009/02/21/css-and-html-loading-full-screen-loading-width-100-height-100.html