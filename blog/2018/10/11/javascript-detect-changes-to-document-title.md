# JavaScript detect changes to document.title

Detect changes to document.title using JavaScript.

```javascript
var target = document.querySelector('title');
var observer = new MutationObserver(function(mutations) {
    mutations.forEach(function(mutation) {
        console.log('title changed to "%s"', document.title);
    });
});
var config = {
    childList: true,
};
observer.observe(target, config);
```

Full example:

```html
<html>
<head>
<title>My Page Title</title>
</head>
<body>

<script>
var target = document.querySelector('title');
var observer = new MutationObserver(function(mutations) {
    mutations.forEach(function(mutation) {
        console.log('title changed to "%s"', document.title);
    });
});
var config = {
    childList: true,
};
observer.observe(target, config);

setTimeout(function() {
    document.title = 'New page title';
}, 5000);
</script>

</body>
</html>
```

---

Posted Oct 11, 2018.

https://www.darklaunch.com/2018/10/11/javascript-detect-changes-to-document-title.html