In the address bar go to `about:config`.
In the Filter: `browser.frames.enabled`
Double click the value to toggle from true to false.
Open a new window for changes to appear.

<img alt="" src="/img/uploads/2013-06/firefox-disable-iframes.png" />

```
about:config
browser.frames.enabled = false
```

---

Posted May 26, 2009.

https://www.darklaunch.com/2009/05/26/firefox-disable-frames-about-config-browser-frames-enabled.html

---

7 comments

<ol><li><div>

anonymous &ndash; Jul 9, 2011<div>

Well is this frames or iframes ?

</div></div><ol><li><div>

anonymous &ndash; Jul 11, 2011<div>

this disables HTML frames

</div></div></li></ol></li><li><div>

anonymous &ndash; Oct 7, 2013<div>

This did not fix the iframe issue.

</div></div></li><li><div>

anonymous &ndash; Oct 8, 2014<div>

browser.frames.enable is not an option :(

</div></div><ol><li><div>

anonymous &ndash; Oct 8, 2014<div>

Mozilla removed the browser.frames.enabled option in Firefox 32.

Bug 1013457 removed this feature.
<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1013457">https://bugzilla.mozilla.org/show_bug.cgi?id=1013457</a>

</div></div></li></ol></li><li><div>

anonymous &ndash; Sep 13, 2015<div>

didn't work. browser.frames is not a found

</div></div><ol><li><div>

anonymous &ndash; Sep 14, 2015<div>

"Bug 1013457 - Remove the browser.frames.enabled pref"
<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=1013457">https://bugzilla.mozilla.org/show_bug.cgi?id=1013457</a>

</div></div></li></ol></li></ol>