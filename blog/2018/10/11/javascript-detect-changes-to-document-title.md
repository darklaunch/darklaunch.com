<p>Detect changes to document.title using JavaScript.</p>

<code name="javascript">
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
</code>

<p>Full example:</p>

<code name="html">
<html>
<head>
<title>My Page Title</title>
</head>
<body>

&lt;script>
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
</code>