```javascript
// Toggle the Bookmarks toolbar
var toolbar = document.getElementById('PersonalToolbar');
toolbar.collapsed = !toolbar.collapsed;

// Toggle the Web Developer toolbar
// see web_developer.xpi/chrome/webdeveloper.jar/content/webdeveloper/webdeveloper.js
var toolbar = document.getElementById('webdeveloper-toolbar');
toolbar.collapsed = !toolbar.collapsed;
```