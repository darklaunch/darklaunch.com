# jQuery open external links in new window

To open external links in new window, use the following jQuery JavaScript:
```javascript
$("a[href^='http:']").not("[href*='" + window.location.hostname + "']").attr('target','_blank');
```

---

Posted Apr 15, 2010.

https://www.darklaunch.com/2010/04/15/jquery-open-external-links-in-new-window.html