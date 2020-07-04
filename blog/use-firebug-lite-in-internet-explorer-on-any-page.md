Use Firebug Lite in Internet Explorer on any page with a simple copy and paste in the URL bar. Firebug provides a lite version for IE to inspect page elements and perform of functions as well.

To use Firebug in <ins>older versions of</ins> Internet Explorer, simply copy and paste the following code into the url and click "Go" or hit the enter key. The code will append the firebug lite script for use on the page and the firebug icon will appear in the bottom right on the page.
```javascript
javascript:var script = document.createElement("script"); script.type = "text/javascript"; script.src = "https://getfirebug.com/firebug-lite.js"; document.getElementsByTagName("body")[0].appendChild(script); void(0);
```

To also open the console, use the following code instead:
```javascript
javascript:var script = document.createElement("script"); script.type = "text/javascript"; script.src = "https://getfirebug.com/firebug-lite.js"; document.getElementsByTagName("body")[0].appendChild(script); script.onreadystatechange = function() { if (script.readyState == "complete") { console.open(); }} void(0);
```

> UPDATE: This method mentioned worked in older versions of IE. For newer versions, use the bookmarklet method. That is, drag the bookmarklet on firebug lite's download page ( http://getfirebug.com/firebuglite ) to your favorites bar. When on the page you want to debug, click the bookmark. Try each of the bookmarklet versions if the stable version doesn't work for you.