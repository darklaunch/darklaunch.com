Write a Greasemonkey userscript for Chrome and Chromium.

```javascript
// ==UserScript==
// @name           My Script
// @match          https://www.example.com/
// ==/UserScript==

console.log('included');

function addJQuery(callback) {
    var script = document.createElement('script');
    script.setAttribute('src', '//ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js');
    script.addEventListener('load', function() {
        var script = document.createElement('script');
        script.textContent = 'window.jQ=jQuery.noConflict(true);(' + callback.toString() + ')();';
        document.body.appendChild(script);
    }, false);
    document.body.appendChild(script);
}

addJQuery(function() {
    console.log('jQuery added', jQ);
    jQ('.selector').find('button').click();
});
```

---

Posted Jan 4, 2014.

https://www.darklaunch.com/2014/01/04/chrome-userscript-extension-template.html