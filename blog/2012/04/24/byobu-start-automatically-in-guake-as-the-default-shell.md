To launch byobu automatically at login, on the command line, run `byobu-enable`. byobu-enable is a "wrapper script for enabling/disabling automatic startup of byobu after login into text console".

```bash
$ byobu-enable
```

Otherwise run byobu and type `F9` to bring up the "Byobu Configuration Menu". Arrow down to "Byobu currently does not launch at login (toggle on)" and hit `enter`. Byobu will now launch at login. Hit `tab` to focus Exit and hit `enter` to leave the configuration menu.

To launch byobu automatically at login within guake, open guake preferences. Check "Run command as a login shell". Now whenever you activate guake, byobu will be instantiated.

---

Posted Apr 24, 2012.

https://www.darklaunch.com/2012/04/24/byobu-start-automatically-in-guake-as-the-default-shell.html

---

6 comments

<ol><li><div>

anonymous &ndash; May 30, 2012<div>

Thank you!! This is what I needed.

</div></div></li><li><div>

anonymous &ndash; Mar 19, 2013<div>

Didn't have login shell box ticked. Thanks!

</div></div></li><li><div>

anonymous &ndash; May 31, 2013<div>

Thanks a lot!
Exactly what I've been looking for.
Ryo

</div></div></li><li><div>

anonymous &ndash; Feb 19, 2016<div>

I just add this comment on related Guake issue: <a href="https://github.com/Guake/guake/issues/71#issuecomment-186029163">https://github.com/Guake/guake/issues/71#issuecomment-186029163</a>

    # apt-get install byobu &amp;&amp; which byobu | tee -a /etc/shells
    Run guake-prefs and change Default interpreter.

</div></div></li><li><div>

anonymous &ndash; Aug 17, 2016<div>

(bow) You have no idea how great the intensity of my excitement was when I found and did this. byobu + guake was my dream. Thank you!

</div></div></li><li><div>

anonymous &ndash; Aug 13, 2017<div>

Perfect. I was missing the last bit. Running as a login shell. Thanks!

</div></div></li></ol>