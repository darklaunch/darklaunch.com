# Control Volume with Keyboard Shortcut in Xfce

Add an Xfce shortcut by going to Applications > Settings > Keyboard. Select the Application Shortcuts tab. Click Add to set volume up, volume down and toggle mute shortcuts:
```
amixer set Master 3+
```
```
amixer set Master 3-
```
For toggling mute:
```
amixer set Master toggle
```
After each code shortcut command is added, press a hotkey to associate it with the command.

---

Posted Feb 15, 2010.

https://www.darklaunch.com/2010/02/15/control-volume-with-keyboard-shortcut-in-xfce.html

---

9 comments

<ol><li><div>

anonymous &ndash; Aug 13, 2012<div>

Thanks! Exactly what I was looking for.

</div></div></li><li><div>

anonymous &ndash; Dec 29, 2012<div>

Love simple tips like these. Thnx!

</div></div></li><li><div>

anonymous &ndash; Apr 4, 2013<div>

Perfect, it worked on my Arch system :-)

</div></div></li><li><div>

anonymous &ndash; Apr 4, 2013<div>

Perfect, it worked on my Arch system :-)

</div></div></li><li><div>

anonymous &ndash; Jun 18, 2013<div>

It helped. Thanks.

</div></div></li><li><div>

anonymous &ndash; Aug 16, 2013<div>

If it doesn't work as expected, add a percent sign like this:
amixer set Master 3%+

</div></div></li><li><div>

anonymous &ndash; Sep 16, 2013<div>

Didn't exactly work on my XFCE4 on debian wheezy - had to use:
"amixer set Master 10%-" and
"amixer set Master 10%+"
instead

</div></div></li><li><div>

anonymous &ndash; Dec 7, 2013<div>

Ã‚Â¡Perfecto! Ahora, Ã‚Â¿unmute no-mute?

</div></div></li><li><div>

anonymous &ndash; Jun 26, 2014<div>

Thank you! I would have thought this would be a no-brainer hotkey, but it actually took me some time to figure out how to do it. But the volume up and down hotkeys work perfectly!

The mute (toggle) command isn't working quite right for me (on Xubuntu 14.04). It works to mute, but it won't work to unmute. Oh well, I don't really need that one. Thank you again!

</div></div></li></ol>