# Firefox Move Tab First, Last

To send the current tab to the beginning or end of the list of currently open tabs, add the following hotkey shortcuts to Keyconfig:

Add "Move Tab First" using keyboard shortcut Alt+Home. This will move the focused tab to the first position in the list.
```javascript
gBrowser.moveTabTo(gBrowser.mCurrentTab, 0);
```

Add "Move Tab Last" using keyboard shortcut Alt+End.  This will move the focused tab to the last position in the list.
```javascript
gBrowser.moveTabTo(gBrowser.mCurrentTab, gBrowser.mTabContainer.childNodes.length - 1);
```

NOTE: Alt+Home is already used by "Home" so i disabled that default shortcut and I am using the Firefox add-on New Tab Homepage. http://www.google.com/search?btnI&q=New+Tab+Homepage

NOTE: This is in addition to my previous post
http://darklaunch.com/2009/09/30/firefox-move-tab-left-and-move-tab-right-with-wrapping-without-requiring-focus

---

Posted Oct 30, 2009.

https://www.darklaunch.com/2009/10/30/firefox-move-tab-first-last.html