To open external links in new window, use the following jQuery JavaScript:
```javascript
$("a[href^='http:']").not("[href*='" + window.location.hostname + "']").attr('target','_blank');
```