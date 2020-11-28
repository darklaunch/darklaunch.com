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

---

6 comments

<ol>
    <li>
        <div>
            anonymous &ndash; Mar 23, 2011
            <div>
                <p>Hi -- with Firefox 4, on initially launching the program, this only makes a blank toolbar appear and disappear at first. </p><p></p><p>You have to manually make the toolbar appear through Firefox's own menus, and then the code above works. But you have to do this every time you close and re-open firefox. </p><p></p><p>Could you post a way to fix this?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Mar 24, 2011
            <div>
                <p>With Firefox 4 the above code still works. The only difference I've found is that the bookmarks toolbar is shown after a restart even if you've used the <code>CTRL</code>+<code>B</code> hotkey to hide it.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; May 6, 2011
            <div>
                <p>solution for blank toolbar</p><p><code>var bar = document.getElementById("PersonalToolbar");</code></p><p><code>setToolbarVisibility(bar, bar.collapsed);</code></p><p></p><p><a>source:http://forums.mozillazine.org/viewtopic.php?f=48&amp;t=72994&amp;start=1860</a></p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 29, 2012
            <div>
                <p>Thanks, I was getting the blank toolbar, then I found the solution for that problem in the comments and it is fixed. Thanks again!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jan 7, 2014
            <div>
                <p>Nice. Works in Iceweasel today 2014-1-7.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 20, 2017
            <div>
                <p>2017 and still works like a charm.</p>
            </div>
        </div>
    </li>
</ol>
