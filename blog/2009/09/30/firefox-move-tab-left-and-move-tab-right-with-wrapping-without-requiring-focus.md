# Firefox Move Tab Left and Move Tab Right with Wrapping (without requiring focus!)

Geany allows you to reorder the document tabs using ALT+Page Up (Move document left) and ALT+Page Down (Move document right). To mimic this behavior in Firefox, do the following:

1. Install Keyconfig (if not already installed).
2. Open Keyconfig and "Add a new key".

Name: Move Tab Right
Code:
```javascript
if (gBrowser.mCurrentTab.nextSibling) {
    gBrowser.moveTabTo(gBrowser.mCurrentTab, gBrowser.mCurrentTab._tPos + 1);
}
else{
    gBrowser.moveTabTo(gBrowser.mCurrentTab, 0);
}
```

3. Select the "Move Tab Right" shortcut and assign it the keyboard shortcut of ALT+Page Down. Click Apply.

4. Add another key.

Name: Move Tab Left
Code:
```javascript
if (gBrowser.mCurrentTab.previousSibling) {
    gBrowser.moveTabTo(gBrowser.mCurrentTab, gBrowser.mCurrentTab._tPos - 1);
}
else {
    gBrowser.moveTabTo(gBrowser.mCurrentTab, gBrowser.mTabContainer.childNodes.length - 1);
}
```

5. Select the "Move Tab Left" shortcut and assign it the keyboard shortcut of ALT+Page Up. Click Apply.

4. Now open a new Firefox window (for changes to take effect) with 3 different tabs open. With the first tab focused, press ALT+Page Down and the tab will move to the right. Move it all the way past the last tab and it will wrap and move to the first tab position.

---

Posted Sep 30, 2009.

https://www.darklaunch.com/2009/09/30/firefox-move-tab-left-and-move-tab-right-with-wrapping-without-requiring-focus.html

---

2 comments

<ol><li><div>

anonymous &ndash; Nov 19, 2010<div>

Worked perfectly!

</div></div></li><li><div>

anonymous &ndash; Mar 4, 2014<div>

This is great

</div></div></li></ol>