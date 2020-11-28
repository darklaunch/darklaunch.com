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

<ol>
    <li>
        <div>
            anonymous &ndash; Aug 13, 2012
            <div>
                <p>Thanks! Exactly what I was looking for.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 29, 2012
            <div>
                <p>Love simple tips like these. Thnx!</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 4, 2013
            <div>
                <p>Perfect, it worked on my Arch system :-)</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Apr 4, 2013
            <div>
                <p>Perfect, it worked on my Arch system :-)</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 18, 2013
            <div>
                <p>It helped. Thanks.</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Aug 16, 2013
            <div>
                <p>If it doesn't work as expected, add a percent sign like this:</p><p>amixer set Master 3%+</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Sep 16, 2013
            <div>
                <p>Didn't exactly work on my XFCE4 on debian wheezy - had to use:</p><p>"amixer set Master 10%-" and</p><p>"amixer set Master 10%+"</p><p>instead</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Dec 7, 2013
            <div>
                <p>Ã‚Â¡Perfecto! Ahora, Ã‚Â¿unmute no-mute?</p>
            </div>
        </div>
    </li>
    <li>
        <div>
            anonymous &ndash; Jun 26, 2014
            <div>
                <p>Thank you! I would have thought this would be a no-brainer hotkey, but it actually took me some time to figure out how to do it. But the volume up and down hotkeys work perfectly!</p><p></p><p>The mute (toggle) command isn't working quite right for me (on Xubuntu 14.04). It works to mute, but it won't work to unmute. Oh well, I don't really need that one. Thank you again!</p>
            </div>
        </div>
    </li>
</ol>
