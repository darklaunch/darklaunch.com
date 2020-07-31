Toggle Firefox Bookmarks Toolbar
Install KeyConfig: http://mozilla.dorando.at/keyconfig.xpi

1. Go to Tools > KeyConfig.
2. [Add a new key]
3. Name: Toggle Firefox Bookmarks Toolbar
4. Code:
```javascript
// Toggle Firefox Bookmarks Toolbar
var b = document.getElementById('PersonalToolbar');
b.collapsed = !b.collapsed;
```
5. Click OK. Type a shortcut (CTRL+B) into the text box. Apply. Close. Open new window for changes.

---

Posted May 10, 2009.

https://www.darklaunch.com/2009/05/10/toggle-firefox-bookmarks-toolbar-keyconfig.html